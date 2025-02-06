# Session Manager

## Overview
The `Session` class is a singleton-based session manager for handling user sessions in a PHP application. It provides methods for setting and retrieving session values, managing user authentication status, handling messages between pages, and destroying sessions.

## Features
- Singleton pattern ensures only one instance of the session is created.
- Methods to set and retrieve session data.
- Manage user authentication status.
- Pass messages between pages.
- Destroy sessions for logging out users.

## Installation
Include the `Session.php` file in your project and use it as needed.

## Usage

### Getting the Singleton Instance
```php
use App\Session;

$session = Session::getInstance();
```

### Setting and Retrieving Session Data
```php
$session->set('username', 'JohnDoe');
$username = $session->get('username'); // Returns 'JohnDoe'
```

### Managing User Authentication
```php
$session->setIsLoggedIn(1); // Set user as logged in with user ID 1

if ($session->isLoggedIn()) {
    echo "User is logged in.";
} else {
    echo "User is not logged in.";
}
```

### Passing Messages Between Pages
```php
$session->setMessage('Account created successfully!');
$message = $session->getMessage(); // Returns 'Account created successfully!'
$session->removeMessage(); // Removes the message from the session
```

### Logging Out (Destroying Session)
```php
$session->logout(); // Clears session data and destroys the session
```

## License
This project is open-source and can be used in any way.
