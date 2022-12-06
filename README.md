# Query-a-Digital-Music-Store
## SQL Project

# 1st Question

## Which Artist We should invite to our rock concert? 

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

ORDER by 2 DESC

LIMIT 10


# 2nd Question

## Which Band is The most Productive?

SELECT a.Name Artist_ ,

       COUNT(t.TrackId) numOf_tracks
       

FROM Artist a

JOIN Album al

on a.ArtistId = al.ArtistId

JOIN Track t

on al.AlbumId = t.AlbumId

GROUP BY 1

ORDER BY 2 DESC

LIMIT 5



# 3rd Question

## Who is the most Successful Sales Agent?

SELECT e.FirstName ,

       e.EmployeeId,
       
       ROUND(SUM(i.Total)) TotalSales
       

FROM Employee e

JOIN Customer c

on e.EmployeeId = c.SupportRepId

JOIN Invoice i

on c.CustomerId = i.CustomerId

GROUP by 1,2



# 4th Question

## Best Countries in terms of total Invoices?

SELECT c.Country ,

       ROUND(SUM(i.total)) Total_Invoices
	   
FROM Customer c

JOIN Invoice i

on c.CustomerId = i.CustomerId

GROUP by 1

ORDER by 2 DESC

LIMIT 10
