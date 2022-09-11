SELECT * FROM demo;

SELECT * FROM Invesment_and_Investor;

SELECT * FROM Invesment_and_Investor;
# 1 

SELECT count(DISTINCT investors) as abc FROM Invesment_and_Investor

CREATE TEMP TABLE Q1 as
SELECT country_code, COUNT(DISTINCT investors) as no_of_investors
FROM Invesment_and_Investor
WHERE country_code != 'unknown'
GROUP by country_code
ORDER by no_of_investors DESC
LIMIT 2

SELECT * FROM Q1

# 2

SELECT COUNT(DISTINCT investors) as count_of_investors
FROM Invesment_and_Investor
WHERE invesment_partner != "unknown"
GROUP by invesment_partner

# 3 
SELECT DISTINCT(funding__round_type) FROM Funding_type

SELECT  funding_round_type, COUNT(DISTINCT investors) as no_of_investors
FROM Invesment_and_Investor
WHERE funding_round_type != "unknown"
GROUP by funding_round_type
ORDER by no_of_investors DESC

# 4

SELECT organization_or_person, COUNT(DISTINCT investors) as no_of_investors
FROM Invesment_and_Investor
WHERE organization_or_person != "unknown"
GROUP by organization_or_person

# 5

SELECT region, COUNT(DISTINCT investors) as no_of_investors
FROM Invesment_and_Investor
WHERE region != 'unknown'
GROUP by region
ORDER by no_of_investors DESC

# 6 

SELECT investors, created_at, updated_at
FROM Invesment_and_Investor
WHERE created_at != "unknown" and updated_at != "unknown"

# 7 

SELECT investors
FROM Invesment_and_Investor
WHERE social_media = 1

# 8 

SELECT * FROM Degree

SELECT degree_type, count(DISTINCT person_name) as no_of_investors
FROM Degree
WHERE degree_type != "unknown"
GROUP by degree_type
ORDER by no_of_investors DESC
LIMIT 5

SELECT subject as Specialization, count(DISTINCT person_name) as no_of_investors
FROM Degree
WHERE subject != "unknown"
GROUP by subject
ORDER by no_of_investors DESC
LIMIT 5

# 9

SELECT acquiree_name_or_invested_in, sum(funding_amount_or_acquisation_amonut) as fund_raised
FROM Invesment_and_Investor
WHERE funding_amount_or_acquisation_amonut != "unknown"
GROUP by acquiree_name_or_invested_in
ORDER by fund_raised DESC
LIMIT 10


SELECT count(DISTINCT acquiree_name_or_invested_in) as No_of_companies_which_got_invesments 
FROM Invesment_and_Investor


# 10 

SELECT sum(funding_amount_or_acquisation_amonut) as Total_funding_amount
FROM Invesment_and_Investor
WHERE funding_amount_or_acquisation_amonut != "unknown"

# 11

SELECT investors, sum(funding_amount_or_acquisation_amonut) as total_funding_amount
FROM Invesment_and_Investor
WHERE funding_amount_or_acquisation_amonut != "unknown"
GROUP by investors
ORDER by total_funding_amount DESC
LIMIT 10

