## Arrays 
### Best Time to Buy and Sell Stock

<details>
  <summary>Hint</summary>
  
  - [x] Track the lowest price while iterating through the prices.
  - [x] Calculate the profit by subtracting the tracked minimum price from each current price.

    <details> 
        The new number is lower than the lowest point found so far, so you update it. The new number is higher than your low point so it is a possible solution and you calculate the difference to find the profit. If it's higher than your max profit found so far, update. <a href="https://www.youtube.com/watch?v=eMSfBgbiEjk"> YouTube Resource </a>
    </details>
    
</details>

<details>
  <summary>Solutions:</summary>
  
  ```java:
  int minprice = Integer.MAX_VALUE;
        int maxprofit = 0;
        for (int i = 0; i < prices.length; i++) {
            if (prices[i] < minprice) {
                minprice = prices[i];
            } else if (prices[i] - minprice > maxprofit) {
                maxprofit = prices[i] - minprice;
            }
        }
        return maxprofit;
  ```
</details>          
