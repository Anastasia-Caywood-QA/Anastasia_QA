SQL my examples

1  chicago_taxi=# SELECT ts AS ts, CASE WHEN description LIKE '%rain%' OR description LIKE '%storm%' THEN 'BAD' ELSE 'GOOD' END AS weather_conditions FROM weather_records WHERE ts BETWEEN '2017-11-05' AND '2017-11-06';

2 chicago_taxi=# SELECT cabs.company_name AS company_name, COUNT (trip_id) AS trip_amount FROM trips INNER JOIN cabs ON cabs.cab_id=trips.cab_id WHERE DATE(start_ts) = '2017-11-15' OR DATE(start_ts) = '2017-11-16' GROUP BY company_name ORDER BY COUNT (trip_id) DESC;

3 chicago_taxi=# SELECT company_name, COUNT(*) CNT FROM cabs  GROUP BY company_name HAVING COUNT(*)<=100 ORDER BY cnt DESC;