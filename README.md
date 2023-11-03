# CSS
css

```
// pages/index.js
import { useState } from 'react';
import Link from 'next/link';

export default function Home() {
  const [authenticated, setAuthenticated] = useState(false);
  const [username, setUsername] = useState('your_username'); // Set your username
  const [password, setPassword] = useState('your_password'); // Set your password

  const handleLogin = () => {
    // Check the entered username and password.
    if (username === 'your_username' && password === 'your_password') {
      setAuthenticated(true);
    } else {
      alert('Invalid credentials');
    }
  };

  const handleLogout = () => {
    setAuthenticated(false);
  };

  return (
    <div>
      {authenticated ? (
        <div>
          <h1>Welcome to the app</h1>
          <button onClick={handleLogout}>Logout</button>
          <Link href="/about">About</Link>
        </div>
      ) : (
        <div>
          <h1>Login</h1>
          <input
            type="text"
            placeholder="Username"
            value={username}
            onChange={(e) => setUsername(e.target.value)}
          />
          <input
            type="password"
            placeholder="Password"
            value={password}
            onChange={(e) => setPassword(e.target.value)}
          />
          <button onClick={handleLogin}>Login</button>
        </div>
      )}
    </div>
  );
}
```
