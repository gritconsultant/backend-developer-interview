# Coding Challenges - Frontend Development
# ความท้าทายการเขียนโค้ด - การพัฒนา Frontend

## Junior Level (0-2 years experience)

### Challenge 1: DOM Manipulation / ความท้าทายที่ 1: การจัดการ DOM

**EN:** Create a function that changes the background color of all elements with a specific class name.

**TH:** สร้างฟังก์ชันที่เปลี่ยนสีพื้นหลังของ element ทั้งหมดที่มี class name เฉพาะ

```javascript
function changeBackgroundColor(className, color) {
    /*
    Change background color of all elements with given class name
    
    Args:
        className: String - CSS class name
        color: String - CSS color value
    
    Example:
        changeBackgroundColor('highlight', 'yellow');
        changeBackgroundColor('error', '#ff0000');
    */
    // Your code here
}
```

**Expected Time / เวลาที่คาดหวัง:** 15 minutes
**Key Concepts / แนวคิดหลัก:** DOM manipulation, querySelector, classList

### Challenge 2: Event Handling / ความท้าทายที่ 2: การจัดการ Event

**EN:** Create a button counter that increases by 1 each time it's clicked.

**TH:** สร้างปุ่มนับที่เพิ่มขึ้น 1 ทุกครั้งที่คลิก

```html
<!DOCTYPE html>
<html>
<head>
    <title>Button Counter</title>
</head>
<body>
    <button id="counter-btn">Count: 0</button>
    
    <script>
        // Your JavaScript code here
        function setupButtonCounter() {
            // Implement counter functionality
        }
        
        // Initialize when page loads
        setupButtonCounter();
    </script>
</body>
</html>
```

**Expected Time / เวลาที่คาดหวัง:** 20 minutes
**Key Concepts / แนวคิาาหลัก:** Event listeners, DOM updates, state management

### Challenge 3: Form Validation / ความท้าทายที่ 3: การตรวจสอบฟอร์ม

**EN:** Create a simple form validation for email and password fields.

**TH:** สร้างการตรวจสอบฟอร์มอย่างง่ายสำหรับช่องอีเมลและรหัสผ่าน

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Validation</title>
    <style>
        .error { color: red; }
        .success { color: green; }
    </style>
</head>
<body>
    <form id="login-form">
        <div>
            <label>Email:</label>
            <input type="email" id="email" required>
            <span id="email-error" class="error"></span>
        </div>
        <div>
            <label>Password:</label>
            <input type="password" id="password" required>
            <span id="password-error" class="error"></span>
        </div>
        <button type="submit">Login</button>
    </form>
    
    <script>
        /*
        Validation Rules:
        - Email: Must be valid email format
        - Password: Minimum 8 characters, at least 1 uppercase, 1 lowercase, 1 number
        */
        // Your code here
    </script>
</body>
</html>
```

**Expected Time / เวลาที่คาดหวัง:** 25 minutes
**Key Concepts / แนวคิดหลัก:** Form validation, Regular expressions, Error handling

## Mid Level (2-5 years experience)

### Challenge 4: Todo List Application / ความท้าทายที่ 4: แอปพลิเคชันรายการงาน

**EN:** Create a todo list application with add, delete, and mark complete functionality.

**TH:** สร้างแอปพลิเคชันรายการงานที่มีฟังก์ชันเพิ่ม ลบ และทำเครื่องหมายเสร็จ

```html
<!DOCTYPE html>
<html>
<head>
    <title>Todo List</title>
    <style>
        .todo-item { margin: 10px 0; }
        .completed { text-decoration: line-through; opacity: 0.6; }
        .delete-btn { margin-left: 10px; color: red; cursor: pointer; }
    </style>
</head>
<body>
    <div id="todo-app">
        <h2>Todo List</h2>
        <div>
            <input type="text" id="todo-input" placeholder="Enter a todo...">
            <button id="add-btn">Add</button>
        </div>
        <ul id="todo-list"></ul>
    </div>
    
    <script>
        class TodoApp {
            constructor() {
                this.todos = [];
                this.nextId = 1;
                this.init();
            }
            
            init() {
                // Initialize event listeners and render
                // Your code here
            }
            
            addTodo(text) {
                // Add new todo
                // Your code here
            }
            
            deleteTodo(id) {
                // Delete todo by id
                // Your code here
            }
            
            toggleComplete(id) {
                // Toggle completion status
                // Your code here
            }
            
            render() {
                // Render todo list
                // Your code here
            }
        }
        
        // Initialize app
        const app = new TodoApp();
    </script>
</body>
</html>
```

**Expected Time / เวลาที่คาดหวัง:** 40 minutes
**Key Concepts / แนวคิดหลัก:** Class-based JavaScript, State management, Dynamic DOM updates

### Challenge 5: API Data Fetching / ความท้าทายที่ 5: การดึงข้อมูลจาก API

**EN:** Create a user list that fetches data from JSONPlaceholder API and displays it with loading states.

**TH:** สร้างรายการผู้ใช้ที่ดึงข้อมูลจาก JSONPlaceholder API และแสดงพร้อมสถานะการโหลด

```html
<!DOCTYPE html>
<html>
<head>
    <title>User List</title>
    <style>
        .loading { text-align: center; font-style: italic; }
        .error { color: red; text-align: center; }
        .user-card { 
            border: 1px solid #ddd; 
            margin: 10px; 
            padding: 15px; 
            border-radius: 5px; 
        }
        .user-name { font-weight: bold; }
        .user-email { color: #666; }
    </style>
</head>
<body>
    <div id="app">
        <h2>Users</h2>
        <button id="load-users">Load Users</button>
        <div id="user-container"></div>
    </div>
    
    <script>
        class UserList {
            constructor() {
                this.users = [];
                this.isLoading = false;
                this.error = null;
                this.init();
            }
            
            init() {
                // Initialize event listeners
                // Your code here
            }
            
            async fetchUsers() {
                /*
                Fetch users from: https://jsonplaceholder.typicode.com/users
                Handle loading states and errors
                */
                // Your code here
            }
            
            render() {
                /*
                Render different states:
                - Loading: Show "Loading users..."
                - Error: Show error message
                - Success: Show user cards with name, email, and website
                */
                // Your code here
            }
        }
        
        // Initialize app
        const userList = new UserList();
    </script>
</body>
</html>
```

**Expected Time / เวลาที่คาดหวัง:** 35 minutes
**Key Concepts / แนวคิดหลัก:** Async/await, Fetch API, Error handling, Loading states

## Senior Level (5+ years experience)

### Challenge 6: Custom Hook Implementation (React-style) / ความท้าทายที่ 6: การติดตั้ง Custom Hook

**EN:** Create a custom hook pattern in vanilla JavaScript that manages local storage state.

**TH:** สร้างรูปแบบ custom hook ใน vanilla JavaScript ที่จัดการสถานะ local storage

```javascript
/*
Create a useLocalStorage hook that:
1. Reads initial value from localStorage
2. Updates localStorage when value changes
3. Provides getter and setter functions
4. Handles JSON serialization/deserialization
5. Provides error handling for invalid JSON

Example usage:
const [count, setCount] = useLocalStorage('count', 0);
const [user, setUser] = useLocalStorage('user', { name: '', email: '' });
*/

function useLocalStorage(key, initialValue) {
    /*
    Custom hook for localStorage state management
    
    Args:
        key: String - localStorage key
        initialValue: Any - default value if key doesn't exist
    
    Returns:
        Array: [currentValue, setValue] - similar to React useState
    */
    // Your implementation here
}

// Demo usage
function createCounterWithPersistence() {
    const [count, setCount] = useLocalStorage('counter', 0);
    
    const container = document.createElement('div');
    container.innerHTML = `
        <h3>Persistent Counter</h3>
        <p>Count: <span id="count-display">${count}</span></p>
        <button id="increment">+</button>
        <button id="decrement">-</button>
        <button id="reset">Reset</button>
    `;
    
    // Add event listeners
    // Your code here
    
    return container;
}
```

**Expected Time / เวลาที่คาดหวัง:** 45 minutes
**Key Concepts / แนวคิดหลัก:** Closures, localStorage API, JSON handling, Functional programming

### Challenge 7: Component-Based Architecture / ความท้าทายที่ 7: สถาปัตยกรรมแบบ Component

**EN:** Create a reusable Modal component with configurable options and event handling.

**TH:** สร้าง Modal component ที่ใช้ซ้ำได้พร้อมตัวเลือกที่กำหนดได้และการจัดการ event

```javascript
/*
Create a Modal component that supports:
1. Configurable title, content, and buttons
2. Show/hide animations
3. Backdrop click to close
4. Escape key to close
5. Focus management
6. Event callbacks (onOpen, onClose, onConfirm)
7. Different sizes (small, medium, large)
*/

class Modal {
    constructor(options = {}) {
        /*
        Options:
        {
            title: 'Modal Title',
            content: 'Modal content...',
            size: 'medium', // 'small', 'medium', 'large'
            closable: true,
            backdrop: true, // Click backdrop to close
            keyboard: true, // ESC key to close
            buttons: [
                { text: 'Cancel', class: 'btn-secondary', action: 'close' },
                { text: 'Confirm', class: 'btn-primary', action: 'confirm' }
            ],
            onOpen: () => {},
            onClose: () => {},
            onConfirm: () => {}
        }
        */
        // Your implementation here
    }
    
    show() {
        // Show modal with animation
        // Your code here
    }
    
    hide() {
        // Hide modal with animation
        // Your code here
    }
    
    destroy() {
        // Clean up event listeners and remove from DOM
        // Your code here
    }
    
    // Private methods
    _createModal() {
        // Create modal HTML structure
        // Your code here
    }
    
    _setupEventListeners() {
        // Setup all event listeners
        // Your code here
    }
    
    _handleKeydown(event) {
        // Handle keyboard events
        // Your code here
    }
}

// Usage example:
function createModalDemo() {
    const showModalBtn = document.createElement('button');
    showModalBtn.textContent = 'Show Modal';
    showModalBtn.onclick = () => {
        const modal = new Modal({
            title: 'Confirm Action',
            content: 'Are you sure you want to delete this item?',
            size: 'medium',
            buttons: [
                { text: 'Cancel', class: 'btn-secondary', action: 'close' },
                { text: 'Delete', class: 'btn-danger', action: 'confirm' }
            ],
            onConfirm: () => {
                console.log('Item deleted!');
                modal.hide();
            }
        });
        modal.show();
    };
    
    return showModalBtn;
}
```

**Expected Time / เวลาที่คาดหวัง:** 60 minutes
**Key Concepts / แนวคิดหลัก:** OOP design, Event delegation, Accessibility, Animation, Component lifecycle

---

## Assessment Criteria / เกณฑ์การประเมิน

### Code Quality / คุณภาพโค้ด (35%)
- **Clean Code / โค้ดที่สะอาด:** Readable, well-structured HTML/CSS/JS
- **Semantic HTML / HTML ที่มีความหมาย:** Proper use of HTML elements
- **CSS Organization / การจัดระเบียบ CSS:** Logical CSS structure and naming
- **JavaScript Best Practices / แนวปฏิบัติที่ดีของ JavaScript:** Modern JS features, proper scoping

### Functionality / การทำงาน (35%)
- **Requirements Fulfillment / การตอบสนองความต้องการ:** Meets all specified requirements
- **User Experience / ประสบการณ์ผู้ใช้:** Intuitive and responsive interface
- **Error Handling / การจัดการข้อผิดพลาด:** Graceful error handling and validation
- **Cross-browser Compatibility / ความเข้ากันได้ข้ามเบราว์เซอร์:** Works across modern browsers

### Technical Skills / ทักษะเทคนิค (30%)
- **DOM Manipulation / การจัดการ DOM:** Efficient DOM operations
- **Event Handling / การจัดการ Event:** Proper event management
- **Async Programming / การเขียนโปรแกรมแบบ Async:** Promises, async/await usage
- **Modern JavaScript / JavaScript สมัยใหม่:** ES6+ features, modules, classes

---

**Languages/Technologies Covered / ภาษา/เทคโนโลยีที่ครอบคลุม:**
- HTML5
- CSS3 (Flexbox, Grid, Animations)
- Vanilla JavaScript (ES6+)
- DOM API
- Fetch API
- Local Storage
- Event Handling
- Responsive Design

**Tools Allowed / เครื่องมือที่อนุญาต:**
- Any code editor
- Browser developer tools
- MDN documentation
- Can I Use website

**Not Allowed / ไม่อนุญาต:**
- External libraries (jQuery, React, etc.) unless specified
- Code generators or AI assistance
- Copying solutions from the internet
