#### Домашнее задание по теме «Проектирование БД. Связи. 3НФ»
студент: Сергей Романов

группа: SQLPY-1

#####Задание 1.

SQL запросы для создания жанров:
```
INSERT INTO genre
	VALUES(1, 'Pop');

INSERT INTO genre
	VALUES(2, 'Rock');
	
INSERT INTO genre
	VALUES(3, 'Classic');
	
INSERT INTO genre
	VALUES(4, 'EDM');
	
INSERT INTO genre
	VALUES(5, 'Rave');
```
SQL запросы для создания исполнителей:
```
INSERT INTO artist
	VALUES(1, 'Billie Eilish');
	
INSERT INTO artist
	VALUES(2, 'The Kooks');

INSERT INTO artist
	VALUES(3, 'Nothing but thieves');
	
INSERT INTO artist
	VALUES(4, 'ДЕТИ RAVE');
	
INSERT INTO artist
	VALUES(5, 'Nizkiz');
	
INSERT INTO artist
	VALUES(6, 'Мукка');

INSERT INTO artist
	VALUES(7, 'Doja Cat');
	
INSERT INTO artist
	VALUES(8, 'Televisor');
```

SQL запросы для создания альбомов:
```
INSERT INTO album
	VALUES(1, 'WHEN WE ALL FALL ASLEEP, WHERE DO WE GO?', 2019, 1);
	
INSERT INTO album
	VALUES(2, 'The best of ... so far', 2017, 2);
	
INSERT INTO album
	VALUES(3, 'Broken machine', 2017, 2);
	
INSERT INTO album
	VALUES(4, 'Фая', 2019, 5);
	
INSERT INTO album
	VALUES(5, 'Синоптик', 2017, 2);
	
INSERT INTO album
	VALUES(6, 'Девочка с каре', 2019, 2);
	
INSERT INTO album
	VALUES(7, 'Purrr!', 2014, 1);
	
INSERT INTO album
	VALUES(8, 'Venture - EP', 2015, 4);
```
SQL запросы для создания треков:
```
INSERT INTO track
	VALUES(1, 'ilomilo', 156, 1);

INSERT INTO track
	VALUES(2, 'you should see me in a crown', 181, 1);
	
INSERT INTO track
	VALUES(3, 'Ooh la', 209, 2);

INSERT INTO track
	VALUES(4, 'Sway', 216, 2);
	
INSERT INTO track
	VALUES(5, 'Broken machine', 234, 3);

INSERT INTO track
	VALUES(6, 'Amsterdam', 272, 3);
	
INSERT INTO track
	VALUES(7, 'Дворовые рейвы', 231, 4);
	
INSERT INTO track
	VALUES(8, 'Хороводы в аду', 149, 4);
	
INSERT INTO track
	VALUES(9, 'Никому', 182, 5);

INSERT INTO track
	VALUES(10, 'Абсолют', 204, 5);
	
INSERT INTO track
	VALUES(11, 'ДЕВОЧКА С КАРЕ', 159, 6);
	
INSERT INTO track
	VALUES(12, 'ОТ ЛУНЫ И ДО НЕБА', 128, 6);
	
INSERT INTO track
	VALUES(13, 'So high', 199, 7);
	
INSERT INTO track
	VALUES(14, 'Beautiful', 226, 7);
	
INSERT INTO track
	VALUES(15, 'Deluxe', 276, 8);
	
INSERT INTO track
	VALUES(16, 'Find That Someone', 228, 8);
```
SQL запросы для создания сборников:
```
INSERT INTO collection
	VALUES(1, 'first', 2011);
	
INSERT INTO collection
	VALUES(2, 'second', 2012);
	
INSERT INTO collection
	VALUES(3, 'third', 2013);
	
INSERT INTO collection
	VALUES(4, 'fourth', 2014);
	
INSERT INTO collection
	VALUES(5, 'fifth', 2015);
	
INSERT INTO collection
	VALUES(6, 'sixth', 2016);
	
INSERT INTO collection
	VALUES(7, 'seventh', 2017);
	
INSERT INTO collection
	VALUES(8, 'eighth', 2018);
```
SQL запросы для создания отношений Артист-Альбом:
```
INSERT INTO artistalbum
	VALUES(1, 1);
	
INSERT INTO artistalbum
	VALUES(2, 2);
	
INSERT INTO artistalbum
	VALUES(3, 3);
	
INSERT INTO artistalbum
	VALUES(4, 4);
	
INSERT INTO artistalbum
	VALUES(5, 5);
	
INSERT INTO artistalbum
	VALUES(6, 6);
	
INSERT INTO artistalbum
	VALUES(7, 7);
	
INSERT INTO artistalbum
	VALUES(8, 8);
```
SQL запросы для создания отношений Артист-Альбом:
```
INSERT INTO genreartist
	VALUES(1, 1);

INSERT INTO genreartist
	VALUES(2, 2);

INSERT INTO genreartist
	VALUES(2, 3);

INSERT INTO genreartist
	VALUES(5, 4);
	
INSERT INTO genreartist
	VALUES(2, 5);

INSERT INTO genreartist
	VALUES(2, 6);

INSERT INTO genreartist
	VALUES(1, 7);

INSERT INTO genreartist
	VALUES(4, 8);
```
SQL запросы для создания отношений Коллекция-Трек:
```
INSERT INTO collectiontracks
	VALUES(1, 1);
	
INSERT INTO collectiontracks
	VALUES(1, 9);
	
INSERT INTO collectiontracks
	VALUES(2, 2);
	
INSERT INTO collectiontracks
	VALUES(2, 10);

INSERT INTO collectiontracks
	VALUES(3, 3);
	
INSERT INTO collectiontracks
	VALUES(3, 11);
	
INSERT INTO collectiontracks
	VALUES(4, 4);
	
INSERT INTO collectiontracks
	VALUES(4, 12);
	
INSERT INTO collectiontracks
	VALUES(5, 5);
	
INSERT INTO collectiontracks
	VALUES(5, 13);
	
INSERT INTO collectiontracks
	VALUES(6, 6);
	
INSERT INTO collectiontracks
	VALUES(6, 14);

INSERT INTO collectiontracks
	VALUES(7, 7);
	
INSERT INTO collectiontracks
	VALUES(7, 15);
	
INSERT INTO collectiontracks
	VALUES(8, 8);
	
INSERT INTO collectiontracks
	VALUES(8, 16);
```
#####Задание 2. 

1. название и год выхода альбомов, вышедших в 2018 году;
```
SELECT albumname, year FROM album
	where year = 2018
```
2. название и продолжительность самого длительного трека;
```
SELECT trackname, tracklength FROM track
	ORDER BY tracklength DESC
	LIMIT 1
```
3. название треков, продолжительность которых не менее 3,5 минуты;
```
SELECT trackname v track
	WHERE tracklength >= 210
```
4. названия сборников, вышедших в период с 2018 по 2020 год включительно;
```
SELECT name FROM collection
	WHERE year BETWEEN 2018 AND 2020
```
5. исполнители, чье имя состоит из 1 слова;
```
SELECT name FROM artist
	WHERE name NOT LIKE '% %';
```
6. название треков, которые содержат слово "мой"/"my".
```
SELECT trackname FROM track
	WHERE trackname LIKE '%my%';
```







	
