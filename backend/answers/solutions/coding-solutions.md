# Coding Challenge Solutions
# คำตอบของความท้าทายการเขียนโค้ด

## Junior Level Solutions / คำตอบระดับ Junior

### Solution 1: Array Manipulation - Find Maximum / หาค่าสูงสุดในอาร์เรย์

```go
import "errors"

func findMax(numbers []int) (int, error) {
    /*
    Find the maximum number in an array
    Time Complexity: O(n)
    Space Complexity: O(1)
    */
    if len(numbers) == 0 {
        return 0, errors.New("array cannot be empty")
    }
    
    maxNum := numbers[0]
    for _, num := range numbers[1:] {
        if num > maxNum {
            maxNum = num
        }
    }
    
    return maxNum, nil
}

// Alternative solution using built-in comparison
func findMaxSimple(numbers []int) (int, error) {
    if len(numbers) == 0 {
        return 0, errors.New("array cannot be empty")
    }
    
    maxNum := numbers[0]
    for _, num := range numbers {
        if num > maxNum {
            maxNum = num
        }
    }
    return maxNum, nil
}

// Test cases
func testFindMax() {
    result1, _ := findMax([]int{1, 3, 2, 8, 5})  // Output: 8
    result2, _ := findMax([]int{-1, -3, -2})     // Output: -1
    result3, _ := findMax([]int{42})             // Output: 42
    
    fmt.Println(result1, result2, result3)
}
```

### Solution 2: String Manipulation - Palindrome Check / ตรวจสอบ Palindrome

```go
import (
    "strings"
    "unicode"
)

func isPalindrome(s string) bool {
    /*
    Check if a string is a palindrome
    Time Complexity: O(n)
    Space Complexity: O(1)
    */
    // Clean the string: remove spaces and convert to lowercase
    cleaned := cleanString(s)
    
    // Two-pointer approach
    left, right := 0, len(cleaned)-1
    
    for left < right {
        if cleaned[left] != cleaned[right] {
            return false
        }
        left++
        right--
    }
    
    return true
}

func cleanString(s string) string {
    var result strings.Builder
    for _, char := range s {
        if unicode.IsLetter(char) || unicode.IsDigit(char) {
            result.WriteRune(unicode.ToLower(char))
        }
    }
    return result.String()
}

// Alternative solution using string reversal
func isPalindromeSimple(s string) bool {
    cleaned := cleanString(s)
    return cleaned == reverseString(cleaned)
}

func reverseString(s string) string {
    runes := []rune(s)
    for i, j := 0, len(runes)-1; i < j; i, j = i+1, j-1 {
        runes[i], runes[j] = runes[j], runes[i]
    }
    return string(runes)
}

// Test cases
func testIsPalindrome() {
    fmt.Println(isPalindrome("racecar"))                    // true
    fmt.Println(isPalindrome("hello"))                      // false
    fmt.Println(isPalindrome("A man a plan a canal Panama")) // true
    fmt.Println(isPalindrome("race a car"))                 // false
}
```

## Mid Level Solutions / คำตอบระดับ Mid

### Solution 3: Two Sum Problem / ปัญหา Two Sum

```go
func twoSum(nums []int, target int) []int {
    /*
    Find two numbers that add up to target
    Time Complexity: O(n)
    Space Complexity: O(n)
    */
    seen := make(map[int]int) // map[value]index
    
    for i, num := range nums {
        complement := target - num
        
        if index, exists := seen[complement]; exists {
            return []int{index, i}
        }
        
        seen[num] = i
    }
    
    return nil // No solution found
}

// Alternative O(n²) solution for comparison
func twoSumBruteForce(nums []int, target int) []int {
    /*
    Brute force approach
    Time Complexity: O(n²)
    Space Complexity: O(1)
    */
    for i := 0; i < len(nums); i++ {
        for j := i + 1; j < len(nums); j++ {
            if nums[i]+nums[j] == target {
                return []int{i, j}
            }
        }
    }
    return nil
}

// Test cases
func testTwoSum() {
    fmt.Println(twoSum([]int{2, 7, 11, 15}, 9))  // [0, 1]
    fmt.Println(twoSum([]int{3, 2, 4}, 6))       // [1, 2]
    fmt.Println(twoSum([]int{3, 3}, 6))          // [0, 1]
}
```

### Solution 4: Binary Tree In-Order Traversal / การท่องไปแบบ In-Order

```go
type TreeNode struct {
    Val   int
    Left  *TreeNode
    Right *TreeNode
}

func inorderTraversal(root *TreeNode) []int {
    /*
    Recursive in-order traversal
    Time Complexity: O(n)
    Space Complexity: O(h) where h is tree height
    */
    var result []int
    inorderHelper(root, &result)
    return result
}

func inorderHelper(node *TreeNode, result *[]int) {
    if node != nil {
        inorderHelper(node.Left, result)   // Visit left subtree
        *result = append(*result, node.Val) // Visit root
        inorderHelper(node.Right, result)  // Visit right subtree
    }
}

// Iterative solution using stack
func inorderTraversalIterative(root *TreeNode) []int {
    /*
    Iterative in-order traversal using stack
    Time Complexity: O(n)
    Space Complexity: O(h)
    */
    var result []int
    var stack []*TreeNode
    current := root
    
    for len(stack) > 0 || current != nil {
        // Go to leftmost node
        for current != nil {
            stack = append(stack, current)
            current = current.Left
        }
        
        // Current is nil, so we backtrack
        current = stack[len(stack)-1]
        stack = stack[:len(stack)-1]
        result = append(result, current.Val)
        
        // Visit right subtree
        current = current.Right
    }
    
    return result
}

// Test case
func testInorderTraversal() {
    // Tree:     1
    //            \
    //             2
    //            /
    //           3
    root := &TreeNode{Val: 1}
    root.Right = &TreeNode{Val: 2}
    root.Right.Left = &TreeNode{Val: 3}
    
    fmt.Println(inorderTraversal(root))  // [1, 3, 2]
}
```

## Senior Level Solutions / คำตอบระดับ Senior

### Solution 5: LRU Cache Implementation / การติดตั้ง LRU Cache

```go
type Node struct {
    key, value int
    prev, next *Node
}

type LRUCache struct {
    /*
    LRU Cache using doubly linked list + hash map
    Time Complexity: O(1) for both get and put
    Space Complexity: O(capacity)
    */
    capacity int
    cache    map[int]*Node
    head     *Node
    tail     *Node
}

func NewLRUCache(capacity int) *LRUCache {
    lru := &LRUCache{
        capacity: capacity,
        cache:    make(map[int]*Node),
        head:     &Node{},
        tail:     &Node{},
    }
    
    // Connect dummy head and tail nodes
    lru.head.next = lru.tail
    lru.tail.prev = lru.head
    
    return lru
}

func (lru *LRUCache) addNode(node *Node) {
    // Add node right after head
    node.prev = lru.head
    node.next = lru.head.next
    
    lru.head.next.prev = node
    lru.head.next = node
}

func (lru *LRUCache) removeNode(node *Node) {
    // Remove an existing node
    prevNode := node.prev
    nextNode := node.next
    
    prevNode.next = nextNode
    nextNode.prev = prevNode
}

func (lru *LRUCache) moveToHead(node *Node) {
    // Move node to head (mark as recently used)
    lru.removeNode(node)
    lru.addNode(node)
}

func (lru *LRUCache) popTail() *Node {
    // Remove node before tail (least recently used)
    lruNode := lru.tail.prev
    lru.removeNode(lruNode)
    return lruNode
}

func (lru *LRUCache) Get(key int) int {
    if node, exists := lru.cache[key]; exists {
        // Move to head (mark as recently used)
        lru.moveToHead(node)
        return node.value
    }
    return -1
}

func (lru *LRUCache) Put(key int, value int) {
    if node, exists := lru.cache[key]; exists {
        // Update existing node
        node.value = value
        lru.moveToHead(node)
    } else {
        // Add new node
        newNode := &Node{key: key, value: value}
        
        if len(lru.cache) >= lru.capacity {
            // Remove LRU node
            lruNode := lru.popTail()
            delete(lru.cache, lruNode.key)
        }
        
        lru.cache[key] = newNode
        lru.addNode(newNode)
    }
}

// Test cases
func testLRUCache() {
    cache := NewLRUCache(2)
    cache.Put(1, 1)
    cache.Put(2, 2)
    fmt.Println(cache.Get(1))    // 1
    cache.Put(3, 3)              // evicts key 2
    fmt.Println(cache.Get(2))    // -1 (not found)
    fmt.Println(cache.Get(3))    // 3
    fmt.Println(cache.Get(1))    // 1
}
```

### Solution 6: Rate Limiter / Rate Limiter

```go
import (
    "sync"
    "time"
)

type RateLimiter struct {
    /*
    Rate limiter using sliding window log
    Time Complexity: O(1) amortized
    Space Complexity: O(n) where n is number of users
    */
    maxRequests int
    windowSize  time.Duration
    requests    map[string][]time.Time
    mu          sync.RWMutex
}

func NewRateLimiter(maxRequests int, windowSize time.Duration) *RateLimiter {
    return &RateLimiter{
        maxRequests: maxRequests,
        windowSize:  windowSize,
        requests:    make(map[string][]time.Time),
    }
}

func (rl *RateLimiter) IsAllowed(userID string) bool {
    rl.mu.Lock()
    defer rl.mu.Unlock()
    
    currentTime := time.Now()
    userRequests := rl.requests[userID]
    
    // Remove old requests outside the window
    cutoff := currentTime.Add(-rl.windowSize)
    validRequests := make([]time.Time, 0)
    
    for _, requestTime := range userRequests {
        if requestTime.After(cutoff) {
            validRequests = append(validRequests, requestTime)
        }
    }
    
    // Check if we can accept new request
    if len(validRequests) < rl.maxRequests {
        validRequests = append(validRequests, currentTime)
        rl.requests[userID] = validRequests
        return true
    }
    
    rl.requests[userID] = validRequests
    return false
}

// Alternative implementation using sliding window counter
type RateLimiterCounter struct {
    /*
    Sliding window counter approach
    More memory efficient but less precise
    */
    maxRequests int
    windowSize  time.Duration
    users       map[string]*UserData
    mu          sync.RWMutex
}

type UserData struct {
    count       int
    windowStart time.Time
}

func NewRateLimiterCounter(maxRequests int, windowSize time.Duration) *RateLimiterCounter {
    return &RateLimiterCounter{
        maxRequests: maxRequests,
        windowSize:  windowSize,
        users:       make(map[string]*UserData),
    }
}

func (rl *RateLimiterCounter) IsAllowed(userID string) bool {
    rl.mu.Lock()
    defer rl.mu.Unlock()
    
    currentTime := time.Now()
    userData, exists := rl.users[userID]
    
    if !exists {
        userData = &UserData{count: 0, windowStart: currentTime}
        rl.users[userID] = userData
    }
    
    // Check if we need to reset the window
    if currentTime.Sub(userData.windowStart) >= rl.windowSize {
        userData.count = 0
        userData.windowStart = currentTime
    }
    
    // Check if request is allowed
    if userData.count < rl.maxRequests {
        userData.count++
        return true
    }
    
    return false
}

// Test cases
func testRateLimiter() {
    limiter := NewRateLimiter(3, 60*time.Second) // 3 requests per minute
    
    // Simulate requests
    fmt.Println(limiter.IsAllowed("user1"))  // true
    fmt.Println(limiter.IsAllowed("user1"))  // true
    fmt.Println(limiter.IsAllowed("user1"))  // true
    fmt.Println(limiter.IsAllowed("user1"))  // false (rate limited)
    
    // Different user should be allowed
    fmt.Println(limiter.IsAllowed("user2"))  // true
}
```

---

## Key Learning Points / จุดสำคัญที่ควรเรียนรู้

### Algorithm Design Principles / หลักการออกแบบอัลกอริทึม

1. **Time vs Space Trade-offs / การแลกเปลี่ยนระหว่างเวลาและพื้นที่**
   - Hash tables for O(1) lookups at cost of O(n) space
   - Two-pointer technique for O(1) space solutions

2. **Data Structure Selection / การเลือกโครงสร้างข้อมูล**
   - Arrays for simple iterations
   - Hash maps for fast lookups
   - Linked lists for dynamic insertions/deletions
   - Trees for hierarchical data

3. **Edge Case Handling / การจัดการกรณีขอบ**
   - Empty inputs
   - Single element arrays
   - Null/undefined values
   - Integer overflow considerations

### System Design Patterns / รูปแบบการออกแบบระบบ

1. **Cache Patterns / รูปแบบการแคช**
   - LRU eviction policy
   - Write-through vs write-back
   - Cache warming strategies

2. **Rate Limiting Patterns / รูปแบบการจำกัดอัตรา**
   - Sliding window vs fixed window
   - Token bucket vs leaky bucket
   - Distributed rate limiting

### Go-Specific Considerations / การพิจารณาเฉพาะของ Go

1. **Memory Management / การจัดการหน่วยความจำ**
   - Garbage collection with minimal manual intervention
   - Slice and map growth patterns
   - Pointer vs value semantics

2. **Concurrency / การทำงานพร้อมกัน**
   - Goroutines for lightweight concurrency
   - Channels for communication
   - Mutex for shared state protection

3. **Error Handling / การจัดการข้อผิดพลาด**
   - Explicit error returns instead of exceptions
   - Error wrapping and unwrapping
   - Graceful degradation patterns

---

**Performance Benchmarks / เกณฑ์มาตรฐานประสิทธิภาพ:**

| Solution | Time Complexity | Space Complexity | Go-Specific Notes |
|----------|----------------|------------------|-------------------|
| Find Max | O(n) | O(1) | Range loop optimization |
| Palindrome | O(n) | O(1) | Unicode handling with runes |
| Two Sum | O(n) | O(n) | Map lookup efficiency |
| Tree Traversal | O(n) | O(h) | Pointer-based tree navigation |
| LRU Cache | O(1) | O(capacity) | Manual memory management for nodes |
| Rate Limiter | O(1) amortized | O(users) | Concurrent safety with RWMutex |
