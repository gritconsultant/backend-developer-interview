# Coding Challenges - Algorithm & Data Structures
# ความท้าทายการเขียนโค้ด - อัลกอริทึมและโครงสร้างข้อมูล

## Junior Level (0-2 years experience)

### Challenge 1: Array Manipulation / ความท้าทายที่ 1: การจัดการอาร์เรย์

**EN:** Write a function that finds the maximum number in an array of integers.

**TH:** เขียนฟังก์ชันที่หาจำนวนที่มากที่สุดในอาร์เรย์ของจำนวนเต็ม

```go
func findMax(numbers []int) int {
    /*
    Find the maximum number in an array
    
    Args:
        numbers: Slice of integers
    
    Returns:
        int: Maximum number in the array
    
    Example:
        findMax([]int{1, 3, 2, 8, 5}) -> 8
        findMax([]int{-1, -3, -2}) -> -1
    */
    // Your code here
    return 0
}
```

**Expected Time Complexity / ความซับซ้อนของเวลาที่คาดหวัง:** O(n)
**Expected Space Complexity / ความซับซ้อนของพื้นที่ที่คาดหวัง:** O(1)
**Time Limit / เวลาที่กำหนด:** 15 minutes

### Challenge 2: String Manipulation / ความท้าทายที่ 2: การจัดการสตริง

**EN:** Write a function that checks if a string is a palindrome (reads the same forwards and backwards).

**TH:** เขียนฟังก์ชันที่ตรวจสอบว่าสตริงเป็น palindrome หรือไม่ (อ่านจากหน้าไปหลังและหลังไปหน้าเหมือนกัน)

```go
func isPalindrome(s string) bool {
    /*
    Check if a string is a palindrome
    
    Args:
        s: String to check
    
    Returns:
        bool: true if palindrome, false otherwise
    
    Example:
        isPalindrome("racecar") -> true
        isPalindrome("hello") -> false
        isPalindrome("A man a plan a canal Panama") -> true (ignoring spaces and case)
    */
    // Your code here
    return false
}
```

**Expected Time Complexity / ความซับซ้อนของเวลาที่คาดหวัง:** O(n)
**Expected Space Complexity / ความซับซ้อนของพื้นที่ที่คาดหวัง:** O(1)
**Time Limit / เวลาที่กำหนด:** 20 minutes

## Mid Level (2-5 years experience)

### Challenge 3: Two Sum Problem / ความท้าทายที่ 3: ปัญหา Two Sum

**EN:** Given an array of integers and a target sum, find two numbers in the array that add up to the target.

**TH:** กำหนดอาร์เรย์ของจำนวนเต็มและผลรวมเป้าหมาย หาสองจำนวนในอาร์เรย์ที่บวกกันได้ผลรวมเป้าหมาย

```go
func twoSum(nums []int, target int) []int {
    /*
    Find two numbers that add up to target
    
    Args:
        nums: Slice of integers
        target: Target sum
    
    Returns:
        []int: Indices of the two numbers, or nil if not found
    
    Example:
        twoSum([]int{2, 7, 11, 15}, 9) -> []int{0, 1}  // nums[0] + nums[1] = 2 + 7 = 9
        twoSum([]int{3, 2, 4}, 6) -> []int{1, 2}       // nums[1] + nums[2] = 2 + 4 = 6
    */
    // Your code here
    return nil
}
```

**Expected Time Complexity / ความซับซ้อนของเวลาที่คาดหวัง:** O(n)
**Expected Space Complexity / ความซับซ้อนของพื้นที่ที่คาดหวัง:** O(n)
**Time Limit / เวลาที่กำหนด:** 25 minutes

### Challenge 4: Binary Tree Traversal / ความท้าทายที่ 4: การท่องไปใน Binary Tree

**EN:** Implement in-order traversal of a binary tree.

**TH:** ติดตั้งการท่องไปแบบ in-order ของ binary tree

```go
type TreeNode struct {
    Val   int
    Left  *TreeNode
    Right *TreeNode
}

func inorderTraversal(root *TreeNode) []int {
    /*
    Perform in-order traversal of binary tree
    
    Args:
        root: *TreeNode - Root of the binary tree
    
    Returns:
        []int: Values in in-order traversal order
    
    Example:
        Tree:     1
                   \
                    2
                   /
                  3
        Result: []int{1, 3, 2}
    */
    // Your code here
    return nil
}
```

**Expected Time Complexity / ความซับซ้อนของเวลาที่คาดหวัง:** O(n)
**Expected Space Complexity / ความซับซ้อนของพื้นที่ที่คาดหวัง:** O(h) where h is height
**Time Limit / เวลาที่กำหนด:** 30 minutes

## Senior Level (5+ years experience)

### Challenge 5: LRU Cache Implementation / ความท้าทายที่ 5: การติดตั้ง LRU Cache

**EN:** Design and implement a Least Recently Used (LRU) cache.

**TH:** ออกแบบและติดตั้ง Least Recently Used (LRU) cache

```go
type LRUCache struct {
    // Your fields here
}

/*
LRU Cache implementation

Operations:
- Get(key): Get value by key, return -1 if not found
- Put(key, value): Put key-value pair, evict LRU if capacity exceeded

Example:
    cache := NewLRUCache(2)
    cache.Put(1, 1)
    cache.Put(2, 2)
    cache.Get(1)       // returns 1
    cache.Put(3, 3)    // evicts key 2
    cache.Get(2)       // returns -1 (not found)
*/

func NewLRUCache(capacity int) *LRUCache {
    /*
    Initialize LRU cache with given capacity
    
    Args:
        capacity: Maximum number of key-value pairs
    */
    // Your code here
    return &LRUCache{}
}

func (cache *LRUCache) Get(key int) int {
    /*
    Get value by key
    
    Args:
        key: Key to look up
    
    Returns:
        int: Value if found, -1 otherwise
    */
    // Your code here
    return -1
}

func (cache *LRUCache) Put(key int, value int) {
    /*
    Put key-value pair
    
    Args:
        key: Key to store
        value: Value to store
    */
    // Your code here
}
```

**Expected Time Complexity / ความซับซ้อนของเวลาที่คาดหวัง:** O(1) for both get and put
**Expected Space Complexity / ความซับซ้อนของพื้นที่ที่คาดหวัง:** O(capacity)
**Time Limit / เวลาที่กำหนด:** 45 minutes

### Challenge 6: Rate Limiter / ความท้าทายที่ 6: Rate Limiter

**EN:** Design a rate limiter that limits the number of requests per user within a time window.

**TH:** ออกแบบ rate limiter ที่จำกัดจำนวนคำขอต่อผู้ใช้ภายในช่วงเวลาที่กำหนด

```go
import (
    "sync"
    "time"
)

type RateLimiter struct {
    // Your fields here
    mu sync.RWMutex
}

/*
Rate limiter implementation using sliding window

Limits requests per user within a time window

Example:
    limiter := NewRateLimiter(5, 60)  // 5 requests per minute
    limiter.IsAllowed("user1")  // true
    // ... 4 more requests for user1 ...
    limiter.IsAllowed("user1")  // false (exceeded limit)
*/

func NewRateLimiter(maxRequests int, windowSize int) *RateLimiter {
    /*
    Initialize rate limiter
    
    Args:
        maxRequests: Maximum requests allowed per window
        windowSize: Time window in seconds
    */
    // Your code here
    return &RateLimiter{}
}

func (rl *RateLimiter) IsAllowed(userID string) bool {
    /*
    Check if request is allowed for user
    
    Args:
        userID: User identifier
    
    Returns:
        bool: true if allowed, false if rate limited
    */
    // Your code here
    return false
}
```

**Expected Time Complexity / ความซับซ้อนของเวลาที่คาดหวัง:** O(1) amortized
**Expected Space Complexity / ความซับซ้อนของพื้นที่ที่คาดหวัง:** O(n) where n is number of users
**Time Limit / เวลาที่กำหนด:** 45 minutes

---

## Assessment Criteria / เกณฑ์การประเมิน

### Code Quality / คุณภาพโค้ด (40%)
- **Clean Code / โค้ดที่สะอาด:** Readable, well-structured code with meaningful variable names
- **Error Handling / การจัดการข้อผิดพลาด:** Appropriate error handling and edge case consideration
- **Documentation / เอกสารประกอบ:** Clear comments and docstrings

### Correctness / ความถูกต้อง (35%)
- **Functionality / การทำงาน:** Code produces correct output for all test cases
- **Edge Cases / กรณีขอบ:** Handles boundary conditions properly
- **Logic / ตรรกศาสตร์:** Sound algorithmic approach

### Efficiency / ประสิทธิภาพ (25%)
- **Time Complexity / ความซับซ้อนของเวลา:** Meets expected time complexity requirements
- **Space Complexity / ความซับซ้อนของพื้นที่:** Efficient memory usage
- **Optimization / การปรับปรุง:** Shows understanding of performance trade-offs

---

**Languages Supported / ภาษาที่รองรับ:**
- Go (Golang)
- Python
- JavaScript/Node.js
- Java
- C#
- PHP

**Tools Allowed / เครื่องมือที่อนุญาต:**
- Any IDE or text editor
- Documentation reference
- Basic calculator

**Not Allowed / ไม่อนุญาต:**
- Internet search for solutions
- AI code generation tools
- Collaboration with others
