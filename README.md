WITH Profit_formula AS (
    SELECT 
        Product_Category, 
        SUM(Quantity_Sold * Sale_Price) AS Revenue, 
        SUM((Quantity_Sold * Sale_Price) - (Quantity_Sold * Cost_Price)) AS Profit
    FROM 
        Sales_Data
    GROUP BY 
        Product_Category
)
SELECT 
    PF.Product_Category, 
    (Profit/Revenue) *100 AS AVG_Profit_Margin 
FROM 
    Profit_formula PF 
ORDER BY 
    AVG_Profit_Margin DESC 


WITH Profit_Calculations AS (
    SELECT 
        Product_Category, 
        SUM(Quantity_Sold * Sale_Price) AS Total_Revenue,  
        SUM((Quantity_Sold * Sale_Price) - (Quantity_Sold * Cost_Price)) AS Total_Profit
    FROM 
        Sales_Data
    GROUP BY 
        Product_Category

<!---
Mmmayen-pf/Mmmayen-pf is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
