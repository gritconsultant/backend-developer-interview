# Frontend Challenge Solutions
# คำตอบของความท้าทายการพัฒนา Frontend

## Junior Level Solutions / คำตอบระดับ Junior

### Solution 1: DOM Manipulation - Change Background Color / เปลี่ยนสีพื้นหลัง

```javascript
function changeBackgroundColor(className, color) {
    /*
    Change background color of all elements with given class name
    Time Complexity: O(n) where n is number of elements
    Space Complexity: O(1)
    */
    
    // Method 1: Using querySelectorAll (recommended)
    const elements = document.querySelectorAll(`.${className}`);
    elements.forEach(element => {
        element.style.backgroundColor = color;
    });
}

// Alternative methods
function changeBackgroundColorAlternative1(className, color) {
    // Method 2: Using getElementsByClassName
    const elements = document.getElementsByClassName(className);
    for (let i = 0; i < elements.length; i++) {
        elements[i].style.backgroundColor = color;
    }
}

function changeBackgroundColorAlternative2(className, color) {
    // Method 3: Using modern array methods
    Array.from(document.getElementsByClassName(className))
        .forEach(element => element.style.backgroundColor = color);
}

// Test cases
function testBackgroundColor() {
    // Create test elements
    document.body.innerHTML += `
        <div class="highlight">Test 1</div>
        <div class="highlight">Test 2</div>
        <div class="other">Test 3</div>
    `;
    
    changeBackgroundColor('highlight', 'yellow');
    changeBackgroundColor('other', '#ff0000');
}
```

### Solution 2: Event Handling - Button Counter / ปุ่มนับ

```html
<!DOCTYPE html>
<html>
<head>
    <title>Button Counter</title>
    <style>
        #counter-btn {
            padding: 10px 20px;
            font-size: 16px;
            border: 2px solid #007bff;
            background-color: #007bff;
            color: white;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        #counter-btn:hover {
            background-color: #0056b3;
        }
        
        #counter-btn:active {
            transform: scale(0.98);
        }
    </style>
</head>
<body>
    <button id="counter-btn">Count: 0</button>
    
    <script>
        function setupButtonCounter() {
            let count = 0;
            const button = document.getElementById('counter-btn');
            
            // Method 1: Basic event listener
            button.addEventListener('click', function() {
                count++;
                button.textContent = `Count: ${count}`;
            });
        }
        
        // Alternative implementation with more features
        function setupAdvancedButtonCounter() {
            let count = 0;
            const button = document.getElementById('counter-btn');
            
            // Load saved count from localStorage
            const savedCount = localStorage.getItem('buttonCount');
            if (savedCount) {
                count = parseInt(savedCount);
                updateButtonText();
            }
            
            function updateButtonText() {
                button.textContent = `Count: ${count}`;
            }
            
            function saveCount() {
                localStorage.setItem('buttonCount', count.toString());
            }
            
            button.addEventListener('click', function() {
                count++;
                updateButtonText();
                saveCount();
                
                // Visual feedback
                button.style.transform = 'scale(0.95)';
                setTimeout(() => {
                    button.style.transform = 'scale(1)';
                }, 100);
            });
            
            // Reset on double-click
            button.addEventListener('dblclick', function() {
                count = 0;
                updateButtonText();
                saveCount();
            });
        }
        
        // Initialize when page loads
        document.addEventListener('DOMContentLoaded', setupButtonCounter);
    </script>
</body>
</html>
```

### Solution 3: Form Validation / การตรวจสอบฟอร์ม

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Validation</title>
    <style>
        .form-group {
            margin-bottom: 15px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        input[type="email"], input[type="password"] {
            width: 100%;
            max-width: 300px;
            padding: 8px 12px;
            border: 2px solid #ddd;
            border-radius: 4px;
            font-size: 14px;
        }
        
        input.valid {
            border-color: #28a745;
        }
        
        input.invalid {
            border-color: #dc3545;
        }
        
        .error {
            color: #dc3545;
            font-size: 12px;
            margin-top: 5px;
        }
        
        .success {
            color: #28a745;
            font-size: 12px;
            margin-top: 5px;
        }
        
        button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }
        
        button:disabled {
            background-color: #6c757d;
            cursor: not-allowed;
        }
    </style>
</head>
<body>
    <form id="login-form">
        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" required>
            <div id="email-error" class="error"></div>
        </div>
        <div class="form-group">
            <label for="password">Password:</label>
            <input type="password" id="password" required>
            <div id="password-error" class="error"></div>
        </div>
        <button type="submit" id="submit-btn" disabled>Login</button>
    </form>
    
    <script>
        class FormValidator {
            constructor() {
                this.form = document.getElementById('login-form');
                this.emailInput = document.getElementById('email');
                this.passwordInput = document.getElementById('password');
                this.submitBtn = document.getElementById('submit-btn');
                
                this.emailError = document.getElementById('email-error');
                this.passwordError = document.getElementById('password-error');
                
                this.isEmailValid = false;
                this.isPasswordValid = false;
                
                this.init();
            }
            
            init() {
                // Real-time validation
                this.emailInput.addEventListener('input', () => this.validateEmail());
                this.passwordInput.addEventListener('input', () => this.validatePassword());
                this.emailInput.addEventListener('blur', () => this.validateEmail());
                this.passwordInput.addEventListener('blur', () => this.validatePassword());
                
                // Form submission
                this.form.addEventListener('submit', (e) => this.handleSubmit(e));
            }
            
            validateEmail() {
                const email = this.emailInput.value.trim();
                const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                
                if (email === '') {
                    this.showError(this.emailInput, this.emailError, 'Email is required');
                    this.isEmailValid = false;
                } else if (!emailRegex.test(email)) {
                    this.showError(this.emailInput, this.emailError, 'Please enter a valid email address');
                    this.isEmailValid = false;
                } else {
                    this.showSuccess(this.emailInput, this.emailError, 'Email is valid');
                    this.isEmailValid = true;
                }
                
                this.updateSubmitButton();
            }
            
            validatePassword() {
                const password = this.passwordInput.value;
                
                // Password requirements: min 8 chars, 1 uppercase, 1 lowercase, 1 number
                const minLength = password.length >= 8;
                const hasUppercase = /[A-Z]/.test(password);
                const hasLowercase = /[a-z]/.test(password);
                const hasNumber = /\d/.test(password);
                
                if (password === '') {
                    this.showError(this.passwordInput, this.passwordError, 'Password is required');
                    this.isPasswordValid = false;
                } else if (!minLength) {
                    this.showError(this.passwordInput, this.passwordError, 'Password must be at least 8 characters');
                    this.isPasswordValid = false;
                } else if (!hasUppercase) {
                    this.showError(this.passwordInput, this.passwordError, 'Password must contain at least 1 uppercase letter');
                    this.isPasswordValid = false;
                } else if (!hasLowercase) {
                    this.showError(this.passwordInput, this.passwordError, 'Password must contain at least 1 lowercase letter');
                    this.isPasswordValid = false;
                } else if (!hasNumber) {
                    this.showError(this.passwordInput, this.passwordError, 'Password must contain at least 1 number');
                    this.isPasswordValid = false;
                } else {
                    this.showSuccess(this.passwordInput, this.passwordError, 'Password is strong');
                    this.isPasswordValid = true;
                }
                
                this.updateSubmitButton();
            }
            
            showError(input, errorElement, message) {
                input.classList.remove('valid');
                input.classList.add('invalid');
                errorElement.textContent = message;
                errorElement.className = 'error';
            }
            
            showSuccess(input, errorElement, message) {
                input.classList.remove('invalid');
                input.classList.add('valid');
                errorElement.textContent = message;
                errorElement.className = 'success';
            }
            
            updateSubmitButton() {
                this.submitBtn.disabled = !(this.isEmailValid && this.isPasswordValid);
            }
            
            handleSubmit(e) {
                e.preventDefault();
                
                // Validate all fields one more time
                this.validateEmail();
                this.validatePassword();
                
                if (this.isEmailValid && this.isPasswordValid) {
                    alert('Form submitted successfully!');
                    // Here you would typically send data to server
                    console.log('Login attempt:', {
                        email: this.emailInput.value,
                        password: '***hidden***'
                    });
                } else {
                    alert('Please fix the errors before submitting');
                }
            }
        }
        
        // Initialize validator when page loads
        document.addEventListener('DOMContentLoaded', () => {
            new FormValidator();
        });
    </script>
</body>
</html>
```

## Mid Level Solutions / คำตอบระดับ Mid

### Solution 4: Todo List Application / แอปพลิเคชันรายการงาน

```html
<!DOCTYPE html>
<html>
<head>
    <title>Todo List</title>
    <style>
        * {
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        
        #todo-app {
            background: white;
            border-radius: 8px;
            padding: 30px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        h2 {
            text-align: center;
            color: #333;
            margin-bottom: 30px;
        }
        
        .input-container {
            display: flex;
            gap: 10px;
            margin-bottom: 30px;
        }
        
        #todo-input {
            flex: 1;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 6px;
            font-size: 16px;
        }
        
        #todo-input:focus {
            outline: none;
            border-color: #007bff;
        }
        
        #add-btn {
            padding: 12px 24px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s;
        }
        
        #add-btn:hover {
            background-color: #0056b3;
        }
        
        #add-btn:disabled {
            background-color: #ccc;
            cursor: not-allowed;
        }
        
        #todo-list {
            list-style: none;
            padding: 0;
        }
        
        .todo-item {
            display: flex;
            align-items: center;
            padding: 15px;
            margin: 10px 0;
            background-color: #f8f9fa;
            border-radius: 6px;
            border-left: 4px solid #007bff;
            transition: all 0.3s ease;
        }
        
        .todo-item:hover {
            background-color: #e9ecef;
            transform: translateX(5px);
        }
        
        .todo-item.completed {
            border-left-color: #28a745;
            opacity: 0.7;
        }
        
        .todo-checkbox {
            margin-right: 15px;
            transform: scale(1.2);
        }
        
        .todo-text {
            flex: 1;
            font-size: 16px;
            transition: all 0.3s ease;
        }
        
        .todo-text.completed {
            text-decoration: line-through;
            color: #6c757d;
        }
        
        .todo-actions {
            display: flex;
            gap: 10px;
        }
        
        .edit-btn, .delete-btn {
            padding: 6px 12px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 12px;
            transition: all 0.3s;
        }
        
        .edit-btn {
            background-color: #ffc107;
            color: #000;
        }
        
        .edit-btn:hover {
            background-color: #e0a800;
        }
        
        .delete-btn {
            background-color: #dc3545;
            color: white;
        }
        
        .delete-btn:hover {
            background-color: #c82333;
        }
        
        .edit-input {
            flex: 1;
            padding: 8px;
            border: 2px solid #007bff;
            border-radius: 4px;
            font-size: 16px;
        }
        
        .stats {
            margin-top: 30px;
            padding: 15px;
            background-color: #e9ecef;
            border-radius: 6px;
            text-align: center;
            color: #495057;
        }
        
        .empty-state {
            text-align: center;
            color: #6c757d;
            font-style: italic;
            padding: 40px;
        }
    </style>
</head>
<body>
    <div id="todo-app">
        <h2>📝 Todo List</h2>
        <div class="input-container">
            <input type="text" id="todo-input" placeholder="Enter a todo..." maxlength="100">
            <button id="add-btn">Add</button>
        </div>
        <ul id="todo-list"></ul>
        <div class="stats" id="stats"></div>
    </div>
    
    <script>
        class TodoApp {
            constructor() {
                this.todos = JSON.parse(localStorage.getItem('todos')) || [];
                this.nextId = this.todos.length > 0 ? Math.max(...this.todos.map(t => t.id)) + 1 : 1;
                this.editingId = null;
                
                this.todoInput = document.getElementById('todo-input');
                this.addBtn = document.getElementById('add-btn');
                this.todoList = document.getElementById('todo-list');
                this.stats = document.getElementById('stats');
                
                this.init();
            }
            
            init() {
                // Event listeners
                this.addBtn.addEventListener('click', () => this.handleAdd());
                this.todoInput.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter') this.handleAdd();
                });
                this.todoInput.addEventListener('input', () => this.updateAddButton());
                
                // Initial render
                this.render();
                this.updateAddButton();
            }
            
            handleAdd() {
                const text = this.todoInput.value.trim();
                if (text) {
                    this.addTodo(text);
                    this.todoInput.value = '';
                    this.updateAddButton();
                    this.todoInput.focus();
                }
            }
            
            addTodo(text) {
                const todo = {
                    id: this.nextId++,
                    text: text,
                    completed: false,
                    createdAt: new Date().toISOString()
                };
                
                this.todos.unshift(todo); // Add to beginning
                this.saveTodos();
                this.render();
            }
            
            deleteTodo(id) {
                if (confirm('Are you sure you want to delete this todo?')) {
                    this.todos = this.todos.filter(todo => todo.id !== id);
                    this.saveTodos();
                    this.render();
                }
            }
            
            toggleComplete(id) {
                const todo = this.todos.find(t => t.id === id);
                if (todo) {
                    todo.completed = !todo.completed;
                    todo.completedAt = todo.completed ? new Date().toISOString() : null;
                    this.saveTodos();
                    this.render();
                }
            }
            
            startEdit(id) {
                this.editingId = id;
                this.render();
                
                // Focus on the edit input
                const editInput = document.querySelector(`[data-edit-id="${id}"]`);
                if (editInput) {
                    editInput.focus();
                    editInput.select();
                }
            }
            
            saveEdit(id, newText) {
                const todo = this.todos.find(t => t.id === id);
                if (todo && newText.trim()) {
                    todo.text = newText.trim();
                    todo.updatedAt = new Date().toISOString();
                    this.saveTodos();
                }
                this.editingId = null;
                this.render();
            }
            
            cancelEdit() {
                this.editingId = null;
                this.render();
            }
            
            updateAddButton() {
                const hasText = this.todoInput.value.trim().length > 0;
                this.addBtn.disabled = !hasText;
            }
            
            saveTodos() {
                localStorage.setItem('todos', JSON.stringify(this.todos));
            }
            
            render() {
                this.renderTodos();
                this.renderStats();
            }
            
            renderTodos() {
                if (this.todos.length === 0) {
                    this.todoList.innerHTML = '<li class="empty-state">No todos yet. Add one above! ✨</li>';
                    return;
                }
                
                this.todoList.innerHTML = this.todos.map(todo => {
                    if (this.editingId === todo.id) {
                        return `
                            <li class="todo-item">
                                <input type="text" 
                                       class="edit-input" 
                                       data-edit-id="${todo.id}"
                                       value="${this.escapeHtml(todo.text)}"
                                       onkeypress="if(event.key==='Enter') todoApp.saveEdit(${todo.id}, this.value); if(event.key==='Escape') todoApp.cancelEdit()"
                                       onblur="todoApp.saveEdit(${todo.id}, this.value)">
                            </li>
                        `;
                    }
                    
                    return `
                        <li class="todo-item ${todo.completed ? 'completed' : ''}">
                            <input type="checkbox" 
                                   class="todo-checkbox"
                                   ${todo.completed ? 'checked' : ''}
                                   onchange="todoApp.toggleComplete(${todo.id})">
                            <span class="todo-text ${todo.completed ? 'completed' : ''}">${this.escapeHtml(todo.text)}</span>
                            <div class="todo-actions">
                                <button class="edit-btn" onclick="todoApp.startEdit(${todo.id})" ${todo.completed ? 'disabled' : ''}>
                                    ✏️ Edit
                                </button>
                                <button class="delete-btn" onclick="todoApp.deleteTodo(${todo.id})">
                                    🗑️ Delete
                                </button>
                            </div>
                        </li>
                    `;
                }).join('');
            }
            
            renderStats() {
                const total = this.todos.length;
                const completed = this.todos.filter(t => t.completed).length;
                const pending = total - completed;
                
                this.stats.innerHTML = `
                    📊 <strong>${total}</strong> total, 
                    ✅ <strong>${completed}</strong> completed, 
                    ⏳ <strong>${pending}</strong> pending
                `;
            }
            
            escapeHtml(text) {
                const div = document.createElement('div');
                div.textContent = text;
                return div.innerHTML;
            }
        }
        
        // Initialize app
        let todoApp;
        document.addEventListener('DOMContentLoaded', () => {
            todoApp = new TodoApp();
        });
    </script>
</body>
</html>
```

### Solution 5: API Data Fetching / การดึงข้อมูลจาก API

```html
<!DOCTYPE html>
<html>
<head>
    <title>User List</title>
    <style>
        * {
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f8f9fa;
        }
        
        #app {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }
        
        h2 {
            text-align: center;
            color: #333;
            margin-bottom: 30px;
        }
        
        #load-users {
            display: block;
            margin: 0 auto 30px;
            padding: 12px 30px;
            background: linear-gradient(45deg, #007bff, #0056b3);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        #load-users:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0,123,255,0.3);
        }
        
        #load-users:disabled {
            background: #ccc;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }
        
        .loading {
            text-align: center;
            font-style: italic;
            color: #666;
            padding: 40px;
        }
        
        .loading::after {
            content: '';
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid #f3f3f3;
            border-top: 3px solid #007bff;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-left: 10px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .error {
            color: #dc3545;
            text-align: center;
            padding: 20px;
            background-color: #f8d7da;
            border: 1px solid #f5c6cb;
            border-radius: 6px;
            margin: 20px 0;
        }
        
        .retry-btn {
            margin-top: 15px;
            padding: 8px 20px;
            background-color: #dc3545;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        
        .retry-btn:hover {
            background-color: #c82333;
        }
        
        .user-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .user-card {
            border: 1px solid #e9ecef;
            border-radius: 10px;
            padding: 20px;
            background: linear-gradient(135deg, #fff, #f8f9fa);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .user-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
            border-color: #007bff;
        }
        
        .user-name {
            font-weight: bold;
            font-size: 18px;
            color: #333;
            margin-bottom: 8px;
        }
        
        .user-email {
            color: #666;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
        }
        
        .user-email::before {
            content: '📧';
            margin-right: 8px;
        }
        
        .user-website {
            color: #007bff;
            text-decoration: none;
            display: flex;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .user-website::before {
            content: '🌐';
            margin-right: 8px;
        }
        
        .user-website:hover {
            text-decoration: underline;
        }
        
        .user-company {
            background-color: #e9ecef;
            padding: 8px 12px;
            border-radius: 15px;
            font-size: 12px;
            color: #495057;
            display: inline-block;
        }
        
        .user-stats {
            text-align: center;
            margin-top: 30px;
            padding: 15px;
            background-color: #e7f3ff;
            border-radius: 8px;
            color: #0056b3;
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div id="app">
        <h2>👥 User Directory</h2>
        <button id="load-users">Load Users</button>
        <div id="user-container"></div>
    </div>
    
    <script>
        class UserList {
            constructor() {
                this.users = [];
                this.isLoading = false;
                this.error = null;
                this.retryCount = 0;
                this.maxRetries = 3;
                
                this.loadButton = document.getElementById('load-users');
                this.container = document.getElementById('user-container');
                
                this.init();
            }
            
            init() {
                this.loadButton.addEventListener('click', () => this.fetchUsers());
                
                // Auto-load on page load
                this.fetchUsers();
            }
            
            async fetchUsers() {
                if (this.isLoading) return;
                
                this.isLoading = true;
                this.error = null;
                this.updateButton();
                this.render();
                
                try {
                    // Add artificial delay to show loading state
                    await new Promise(resolve => setTimeout(resolve, 1000));
                    
                    const response = await fetch('https://jsonplaceholder.typicode.com/users');
                    
                    if (!response.ok) {
                        throw new Error(`HTTP error! status: ${response.status}`);
                    }
                    
                    const data = await response.json();
                    
                    // Validate data structure
                    if (!Array.isArray(data)) {
                        throw new Error('Invalid data format received');
                    }
                    
                    this.users = data;
                    this.retryCount = 0;
                    
                } catch (error) {
                    console.error('Error fetching users:', error);
                    this.error = error.message;
                    this.retryCount++;
                } finally {
                    this.isLoading = false;
                    this.updateButton();
                    this.render();
                }
            }
            
            async retryFetch() {
                if (this.retryCount < this.maxRetries) {
                    await this.fetchUsers();
                } else {
                    alert('Maximum retry attempts reached. Please check your connection and try again later.');
                }
            }
            
            updateButton() {
                this.loadButton.disabled = this.isLoading;
                this.loadButton.textContent = this.isLoading ? 'Loading...' : 'Reload Users';
            }
            
            render() {
                if (this.isLoading) {
                    this.container.innerHTML = '<div class="loading">Loading users...</div>';
                    return;
                }
                
                if (this.error) {
                    this.container.innerHTML = `
                        <div class="error">
                            <strong>Error loading users:</strong><br>
                            ${this.escapeHtml(this.error)}
                            <br>
                            <button class="retry-btn" onclick="userList.retryFetch()">
                                Retry (${this.retryCount}/${this.maxRetries})
                            </button>
                        </div>
                    `;
                    return;
                }
                
                if (this.users.length === 0) {
                    this.container.innerHTML = '<div class="loading">No users found.</div>';
                    return;
                }
                
                const userCards = this.users.map((user, index) => `
                    <div class="user-card fade-in" style="animation-delay: ${index * 0.1}s" onclick="userList.showUserDetails(${user.id})">
                        <div class="user-name">${this.escapeHtml(user.name)}</div>
                        <div class="user-email">${this.escapeHtml(user.email)}</div>
                        <a href="http://${this.escapeHtml(user.website)}" target="_blank" class="user-website" onclick="event.stopPropagation()">
                            ${this.escapeHtml(user.website)}
                        </a>
                        <div class="user-company">${this.escapeHtml(user.company.name)}</div>
                    </div>
                `).join('');
                
                this.container.innerHTML = `
                    <div class="user-grid">
                        ${userCards}
                    </div>
                    <div class="user-stats">
                        📊 Showing ${this.users.length} users
                    </div>
                `;
            }
            
            showUserDetails(userId) {
                const user = this.users.find(u => u.id === userId);
                if (user) {
                    const details = `
                        Name: ${user.name}
                        Username: ${user.username}
                        Email: ${user.email}
                        Phone: ${user.phone}
                        Website: ${user.website}
                        Company: ${user.company.name}
                        Address: ${user.address.street}, ${user.address.city}
                    `;
                    alert(details);
                }
            }
            
            escapeHtml(text) {
                const div = document.createElement('div');
                div.textContent = text;
                return div.innerHTML;
            }
        }
        
        // Initialize app
        let userList;
        document.addEventListener('DOMContentLoaded', () => {
            userList = new UserList();
        });
        
        // Handle network connectivity
        window.addEventListener('online', () => {
            console.log('Connection restored');
            if (userList && userList.error) {
                userList.fetchUsers();
            }
        });
        
        window.addEventListener('offline', () => {
            console.log('Connection lost');
        });
    </script>
</body>
</html>
```

---

## Key Learning Points / จุดสำคัญที่ควรเรียนรู้

### Frontend Development Principles / หลักการพัฒนา Frontend

1. **DOM Manipulation Best Practices / แนวปฏิบัติที่ดีในการจัดการ DOM**
   - Use `querySelector` and `querySelectorAll` for modern element selection
   - Prefer `addEventListener` over inline event handlers
   - Batch DOM updates to minimize reflow/repaint

2. **Event Handling Patterns / รูปแบบการจัดการ Event**
   - Event delegation for dynamic content
   - Proper event listener cleanup
   - Keyboard accessibility support

3. **Form Validation Strategies / กลยุทธ์การตรวจสอบฟอร์ม**
   - Real-time validation for better UX
   - Client-side validation with server-side backup
   - Clear error messaging and visual feedback

### Modern JavaScript Techniques / เทคนิค JavaScript สมัยใหม่

1. **ES6+ Features / ฟีเจอร์ ES6+**
   - Template literals for string interpolation
   - Arrow functions and proper `this` binding
   - Destructuring and spread operators
   - Classes and modules

2. **Async Programming / การเขียนโปรแกรมแบบ Async**
   - Promises and async/await patterns
   - Error handling in async operations
   - Loading states and user feedback

3. **Local Storage and State Management / การจัดการ Local Storage และ State**
   - Persistent data storage
   - JSON serialization/deserialization
   - State synchronization across components

### User Experience Considerations / การพิจารณาประสบการณ์ผู้ใช้

1. **Progressive Enhancement / การปรับปรุงแบบก้าวหน้า**
   - Core functionality works without JavaScript
   - Enhanced experience with JavaScript enabled
   - Graceful degradation for older browsers

2. **Accessibility (a11y) / การเข้าถึง**
   - Semantic HTML structure
   - Proper ARIA labels and roles
   - Keyboard navigation support
   - Screen reader compatibility

3. **Performance Optimization / การปรับปรุงประสิทธิภาพ**
   - Minimize DOM queries
   - Use event delegation efficiently
   - Implement loading states
   - Optimize animations and transitions

---

**Frontend Performance Benchmarks / เกณฑ์มาตรฐานประสิทธิภาพ Frontend:**

| Solution | DOM Operations | Event Efficiency | UX Features |
|----------|----------------|------------------|-------------|
| DOM Manipulation | O(n) querySelectorAll | Single event listener | Visual feedback |
| Button Counter | O(1) updates | Direct event binding | Persistent state |
| Form Validation | O(1) per field | Real-time validation | Progressive disclosure |
| Todo List | O(n) rendering | Event delegation | Local storage |
| API Fetching | O(n) card creation | Async state management | Loading states |

**Browser Compatibility Notes / หมายเหตุความเข้ากันได้ของเบราว์เซอร์:**
- All solutions use modern JavaScript (ES6+)
- Compatible with Chrome 60+, Firefox 55+, Safari 12+, Edge 79+
- Graceful degradation for older browsers where applicable
- Progressive enhancement principles applied
