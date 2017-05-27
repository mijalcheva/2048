#2048

Имплементација на играта 2048 во Visual Studio 2010 (C# програмски јазик).

- Проект по предметот Визуелно програмирање на :
•	Стефан Андонов 151020
•	Бојана Мијалчева 151030


#Историја на играта
2048 е лизгачки блок мозаик игра за еден играч, измислена од италијанскиот web developer Gabriele Cirulli.
Оригинално е напишана во JavaScript и CSS.
Поради огромната заинтерсираност за играта(4 милиони луѓе за помалку од една недела), Gabriele објавил слободна апликација за IOS и Android во 2014 и така играта станува хит.
Токму ваквата популарност не предизвика да се обидеме да ја имплементираме оваа игра.


#Како се игра оваа игра?
На прв поглед изгледа многу лесно,
Површина од 4x4 се состои од нумерирани плочки чии вредности играчот ги движи со помош на четирите стрелки на тастатурата. 
Во секој чекор, нова вредност(2 или 4) се генерира случајно на празните места на таблата.
"Плочките" се движат се додека не бидат сопрени од друга плочка или од sидот на таблата. 
Кога две плочки со иста вредност при движењето ќе се спојат се добива една плочка со збирот на вредностите на плочките кои се споиле.
Целта на играта е да се постигне поле со вредност 2048!

#Почетна состојба на играта
_
 

На почетокот случајно се генерираат вредностите на две плочки (вредноста може да биде 2 или 4) и играта започнува со кликање на било која од стрелките на тастатурата.
Со кликање на копчето "New Game" играта започнува одново, односно се прикажува нова почетна состојба. 



#Решение на проблемот
- За чување на податоците користиме матрица во која ги чуваме  вредностите на плочките, 0 означува дека плочката е празна.
Контролите на формата ги чуваме во листа која ја полниме со следнава функција: 

 
- Функцијата generateStart()  ја генерира почетната состојба опишана погоре додека функцијата generateNumberAfterMove() после секој чекор генерира вредност 2 на случајна празна плочка само доколку има можност за потег.
- Функциите toRight(), toLeft(), toUp() и toDown() ја извршуваат најголемата функционалност на апликацијата, тие ги придвижуваат плочките во соодветната насока,кон ѕидовите на таблата, и проверуваат во секоја редица дали постојат плочки кои можат да се спојат. 
 
Имплементацијата на останатите три функции е иста, секако се разликува во делот на придвижувањето во соодветна насока(лево,горе и долу).

•	Играта завршува кога нема повеќе можни чекори, односно таблата е полна и не постојат плочки кои може да се соберат, или е постигната целта, плочка со вредност 2048.
    








