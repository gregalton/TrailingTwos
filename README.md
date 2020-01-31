# TrailingTwos
  A recent live coding challenge
  Given an array, search for 2s and move to the end of the array

    let givenArray = [3,2,2,4,5]

    let resultArray = trailingTwos(startArray: givenArray)
    print(resultArray)

    func trailingTwos(startArray: [Int]) -> [Int] {
        var startArrayCopy = startArray
        var tempArray = [Int]()
        for _ in startArrayCopy {
            if let idx = startArrayCopy.firstIndex(where: { $0 == 2 }) {
                tempArray.append(startArrayCopy.remove(at: idx))
            }
        }
        
        /* Produces an unexpected result of [3, 2, 5, 2, 2]
        for (index, val) in startArrayCopy.enumerated() {
            if val == 2 {
                startArrayCopy.remove(at: index)
                tempArray.append(val)
            }
        }
        */
        
        startArrayCopy.append(contentsOf: tempArray)
        return startArrayCopy
    }
