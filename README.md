# Query-a-Digital-Music-Store
SQL Project

# 1st Question

#Which Artist We should invite to our rock concert? 

SELECT a.Name Artist_ ,
       COUNT(g.Name) Rocks

FROM Artist a
JOIN Album al
on a.ArtistId = al.ArtistId
JOIN Track t
on al.AlbumId = t.AlbumId
JOIN Genre g
on t.GenreId = g.GenreId
WHERE g.Name = 'Rock'
GROUP By 1
order by 2 DESC
limit 10
