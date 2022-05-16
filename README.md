## Задача 1. Самая бесполезная коробка

### Описание
Мы узнали про volatile-переменные, в каких случаях они используются. Попробуем написать реализацию игрушки [cамая бесполезная коробка](http://www.youtube.com/watch?v=tGCW8xftdOA). Один поток будет выключать тумблер, а второй будет эмулировать пользователя, то есть включать тумблер с какой-то периодичностью

### Работа программы
1. Создание поток-пользователь и поток-игрушка
2. Поток-пользователь раз в несколько секунд включает тумблер
3. Поток-игрушка как только обнаруживает включение - выключает тумблер
4. Поток-пользователь, после нескольких итераций завершает выполнение
5. Главный поток (main) после завершения потока-пользователя, останавливает поток-игрушку

### Требования к программе
1. Включение и выключение тумблера должно сопровождаться выводами в консоль
2. Все задержки (кол-во итераций работы потока, периодичность включения) должны быть оформлены в константах (никаких "Магических чисел")

<details>
  <summary>Подсказка</summary>
  
  1. Тумблер используется более, чем одним потоком
  2. Чтобы отловить завершение потока-пользователя, можно использовать join() из лекции по синхронизации
  3. В потоке-игрушке нужно реализовать возможность прерывания потока (см. лекцию по работе с потоками)
</details>

