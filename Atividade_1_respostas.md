
Respostas:
1.Consulta:
```
sqlite> SELECT birth FROM people WHERE name = 'Jerry Seinfeld';
```
1.Resposta:
```
1954
```
2.Consulta:
```
sqlite> SELECT count(*) FROM ratings WHERE rating = 10.0;
```
2.Resposta:
```
count(*)
27
```
3.Consulta:
```
sqlite> SELECT * FROM genres WHERE show_id = (
  SELECT id FROM shows WHERE title = 'The Crown');
```
3.Resposta:
```
show_id | genre
4786824 | Drama
4786824 | History
```
4.Consulta:
4.1 - Consultas separadas
```
sqlite> SELECT id FROM shows WHERE title = 'Arrested Development'
sqlite> SELECT person_id FROM writers WHERE show_id = 367279;
sqlite> SELECT name FROM people WHERE id = 403804;
```
4.2 - Todas as consultas aninhadas
```
sqlite> SELECT name FROM people WHERE id =
        (SELECT person_id FROM writers WHERE show_id =
        (SELECT id FROM shows WHERE title = 'Arrested Development'));

```
4.Resposta:
```
name
Mitchell Hurwitz
```
5.Consultas:
5.1 - Consultas separadas
```
sqlite> SELECT id from people where name = 'Allison Janney';
sqlite> SELECT * FROM shows WHERE id IN (SELECT show_id FROM stars WHERE person_id = 5049);
```
5.1 - Consultas aninhadas
```
sqlite> SELECT title FROM shows WHERE id IN
        (SELECT show_id FROM stars WHERE person_id =
        (SELECT id from people where name = 'Allison Janney'));
```
5.Respostas:
5.1.

```
id
5049
```

5.2.

```
id | title | year | episodes
101148 | Morton & Hayes | 1991 | 6
200276 | The West Wing | 1999 | 155
200370 | The Richard and Judy Show | 1993 | 3
1012987 | The EcoZone Project | 2007 |
1583638 | Mr. Sunshine | 2011 | 13
2660806 | Mom | 2013 | 153
3215260 | The Adventures of Mr. Clown | 2013 | 49
3261668 | Break a Hip | 2015 | 16
4280606 | The Late Late Show with James Corden | 2015 | 828
5333712 | I'll Have What Phil's Having | 2015 | 6
```

