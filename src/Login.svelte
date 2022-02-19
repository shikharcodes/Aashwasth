<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>

<label for="username" style="font-size: large; font-weight:600">Username</label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />

<label for="password" style="font-size: large; font-weight:600">Password</label>
<input name="password" bind:value={password} type="password" />

<button class="login" style="font-weight: 600;" on:click={login}>Login</button>
<button class="login" style="font-weight: 600;" on:click={signup}>Sign Up</button>
  
