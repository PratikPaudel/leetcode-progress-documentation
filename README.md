## Arrays 

### Two Sum

<details>
  <summary>Hint</summary>
  
  - [x] Use a HashMap to store numbers and their indices.
  - [x]  For each number in the array, compute its complement to reach the target.
  - [x]  Check if the complement is in the HashMap: If yes, return the current index and the index of the complement.
    If no, add the number and its index to the HashMap.

    <details> 
        To find two numbers in an array that add up to a target, use a HashMap for quick lookups. As you iterate through the array, calculate the complement needed to reach the target for each number. Check if this complement is already in the HashMap. If it is, return the indices of the current number and the complement. If not, store the current number and its index in the HashMap for future reference. This method allows you to find the solution efficiently in one pass through the array.
    </details>
    
</details>

<details>
  <summary>Solutions:</summary>
  
  ```java:
  if (nums == null || nums.length < 2) {
            throw new IllegalArgumentException("Invalid input array");
        }
        HashMap<Integer, Integer> map = new HashMap<>();
        int[] result = new int[2];
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                result[0] = i;
                result[1] = map.get(complement);
                return result; 
            }
            map.put(nums[i], i);
        }
  ```
</details>          

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
