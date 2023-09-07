### Step 1
*Вывести Альбомы артистов, где ИД артиста от 1 до 10*
```
SELECT * FROM Albums
WHERE artist_id > 0 AND artist_id < 13;
```

### Step 2
*Вывести таблицу, где каждого трека будет указано имя альбома и имя артиста*
```
SELECT Tracks.id, Art.name, Album.name
FROM ((Tracks INNER JOIN Album ON Tracks.album_id = Album.id)
INNER JOIN Artist Art ON Art.id = Album.artist_id);
```
