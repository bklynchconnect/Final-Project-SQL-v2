# Starting with Data
---


## Question 1
> What is the total transaction revenue for each possible channel grouping?

```sql
SELECT
	channel_grouping,
	SUM(
		CASE
			WHEN total_transaction_revenue IS NULL THEN 0
			ELSE total_transaction_revenue
		END
	) AS channel_revenue
FROM all_sessions
GROUP BY channel_grouping
ORDER BY channel_revenue DESC
```

### :heavy_check_mark: Answer

![answer_4_1](./images/starting_with_data_q1.png)

|channel_grouping|channel_revenue|
|----------------|---------------|
|Referral        |6018680000     |
|Direct          |4704190000     |
|Organic Search  |3163670000     |
|Paid Search     |394770000      |
|Affiliates      |0              |
|Display         |0              |
|(Other)         |0              |


