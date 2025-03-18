# TurkStundentCoOdev2
SELECT COUNT(*) AS null_records
FROM Invoice
WHERE invoice_id IS NULL
AND customer_id IS NULL
AND invoice_date IS NULL
AND billing_address IS NULL
AND billing_city IS NULL
AND billing_state IS NULL
AND billing_country IS NULL
AND billingpostal_code IS NULL
AND total IS NULL;
--total rows:1

SELECT invoice_id,total AS orginal_total,
total*2 AS update_total
FROM Invoice
ORDER BY update_total DESC;
--------

SELECT 
	CONCAT(
		SUBSTRING(billing_address FROM 1 FOR 3),
		SUBSTRING(billing_address FROM LENGTH(billing_address)-3 FOR 4)
	) AS "Açık Adres"
FROM Invoice
WHERE 
	EXTRACT(YEAR FROM invoice_date)=2013
	AND EXTRACT(MONTH FROM invoice_date)=8;
