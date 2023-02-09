# HomeWork12

SELECT COUNT(*) FROM film
WHERE length>
(
SELECT AVG(length) FROM film
);



SELECT COUNT(*) FROM film
WHERE rental_rate=
(
SELECT MAX(rental_rate) FROM film
);



SELECT * FROM film
WHERE rental_rate=
(
SELECT MIN(rental_rate) FROM film
)
AND replacement_cost=
(
SELECT MIN(replacement_cost) FROM film
);


SELECT payment.customer_id,customer.first_name,customer.last_name,COUNT(payment.payment_id) AS siparis_adedi
FROM payment
JOIN customer ON customer.customer_id = payment.customer_id
GROUP BY payment.customer_id , customer.first_name , customer.last_name
ORDER BY siparis_adedi DESC
LIMIT 10;
