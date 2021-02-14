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
    
    
    
2. Get largest number from string
Input: 132
Output: 321
Input: 123456789
Output: 987654321

Solution - 

    func getLargestNumber(_ string: String) -> String {

        guard string.count > 0 else {
            return ""
        }

        var array = string.compactMap { Int(String($0)) }

        var largestNumber = array.first!
        var largestNumberIndex = 0

        for (index, number) in array.enumerated() {

            if number > largestNumber {
                largestNumber = number
                largestNumberIndex = index
            }
        }

        array.remove(at: largestNumberIndex)

        let newArray = array.map { String($0) }

        let newString = newArray.joined()

        print(largestNumberIndex, largestNumber, newString)

        return "\(largestNumber)" + getLargestNumber(newString)
    }

    getLargestNumber("19848301023")
    getLargestNumber("1234567890")

