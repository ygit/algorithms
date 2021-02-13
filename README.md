# Algorithms

1. Maximum Pairwise Product
Given a sequence of n non-negative integers to find the maximum pairwise product.
Input: [1,2,3] 
Output: 6
Input: [5,6,7]
Output: 42

Solution - 

    func maximumPairwiseProduct(array: [Int]) -> Int? {
    
      guard var maxProduct = array.first else {
          return nil
      }
    
      for (index, number) in array.enumerated() {
        
        var anotherIndex = index + 1
        
        while anotherIndex < array.count {
            
            let anotherNumber = array[anotherIndex]
            
            let product = number * anotherNumber
            
            if product > maxProduct {
                maxProduct = product
            }
            
            anotherIndex += 1
        }
        
      }
    
      return maxProduct
    }

    maximumPairwiseProduct(array: [5,6,7]) => 42
