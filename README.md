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

### Contains Duplicate

<details>
  <summary>Hint</summary>
  
  - [x] Create a HashSet to store seen integers.
  - [x] Loop through each integer in the array.
  - [x] Try to add each integer to the HashSet.
  - [x] If adding the integer returns false, return true (found a duplicate).
  - [x] If the loop completes without finding duplicates, return false.
        
</details>

<details>
  <summary>Solutions:</summary>
  
  ```java:
 public boolean containsDuplicate(int[] nums) {
        Set<Integer> set = new HashSet<Integer>();
        for (int num : nums) {
            if (set.contains(num)) {
                return true;
            }
            set.add(num);
        }
        return false;
    }
  ```
</details>          

### Product of Array Except Self

<details>
  <summary>Hint</summary>
  
  - [x] Create prefixProducts, suffixProducts, and resultArray arrays.
  - [x] Set prefixProducts[0] to 1 and suffixProducts[length-1] to 1.
  - [x] Iterate from left to right, storing cumulative products in prefixProducts.
  - [x] Iterate from right to left, storing cumulative products in suffixProducts.
  - [x] Multiply corresponding elements of prefixProducts and suffixProducts to fill resultArray.
  - [x] Return the final resultArray.
  - [ ] <a href="https://www.youtube.com/watch?v=tSRFtR3pv74"> YouTube </a>
</details>

<details>
  <summary>Solutions:</summary>
  
  ```java:
        int length = nums.length;
        int[] prefixProducts = new int[length];
        prefixProducts[0] = 1;
        int[] suffixProducts = new int[length];
        suffixProducts[length - 1] = 1;
        int[] resultArray = new int[length];

        for (int i = 1; i < length; i++) {
            prefixProducts[i] = nums[i - 1] * prefixProducts[i - 1];  
        }

        for (int i = length - 2; i >= 0; i--) {
            suffixProducts[i] = nums[i + 1] * suffixProducts[i + 1];
        }

        for (int i = 0; i < length; i++) {
            resultArray[i] = prefixProducts[i] * suffixProducts[i];   
        }

        return resultArray;
  ```
</details>      

### Maximum Subarray

<details>
  <summary>Hint</summary>

  - [x] Initialize Variables: Set maxSum to Integer.MIN_VALUE and currSum to 0.
  - [x] Iterate Through the Array: Add each element to currSum.
  - [x] Update maxSum: Set maxSum to the greater of maxSum and currSum.
  - [x] Reset currSum if Negative: If currSum is less than 0, reset it to 0.
  - [x] Return maxSum: After the loop, return maxSum.
  - [ ] <a href="https://www.youtube.com/watch?v=hLPkqd60-28"> YouTube Link </a>
  
</details>

<details>
  <summary>Solutions:</summary>
  
  ```java:
        int maxSum = Integer.MIN_VALUE;
        int currSum = 0;
        for(int i=0; i<nums.length; i++) {
            currSum += nums[i];
            maxSum = Math.max(maxSum, currSum);
            if (currSum < 0) {
                currSum = 0;
            }
        } return maxSum;
  ```
</details>

### Maximum Product Subarray

<details>
  <summary>Hint</summary>

   - [x] Initialization: Create prefix and suffix variables, initialize both to 1, and initialize result to 0.
   - [x] Iteration: Loop through the array from 0 to n-1.
   - [x] Reset Prefix and Suffix: If prefix or suffix is 0, reset it to 1.
   - [x] Update Prefix and Suffix: Multiply prefix by nums[i] and suffix by nums[n-i-1].
   - [x] Update Result: Use Math.max to set result to the maximum of result, prefix, and suffix.
   - [x] Return Result: Cast result to int and return it.
   - [ ] <a href="https://www.youtube.com/watch?v=hnswaLJvr6g"> YouTube </a>
  
</details>

<details>
  <summary>Solutions:</summary>
  
  ```java:
        int n= nums.length;
        double prefix = 1;
        double suffix = 1;
        double result = 0;
        if(n == 1) return nums[0];
        for (int i=0; i<n; i++) {
            if (prefix == 0) { prefix = 1;}
            if (suffix == 0) { suffix = 1;}
            prefix *= nums[i];
            suffix *= nums[n-i-1];
            result = Math.max(result, Math.max(prefix, suffix)); 
        }
        return (int) result;
  ```

</details>

