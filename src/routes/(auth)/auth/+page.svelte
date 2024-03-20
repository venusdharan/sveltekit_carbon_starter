<script>
    import { Grid, Row, Column, Form, FormGroup, TextInput, PasswordInput, Button } from 'carbon-components-svelte';
  
    let email = '';
    let password = '';
  
    const handleLogin = (event) => {
      event.preventDefault();
      // Handle login logic here (e.g., send login credentials to your backend)
      console.log('Login attempted:', email, password);
    };
  </script>
  
  <style>
    .login-container {
      min-height: 80vh;
    }
  </style>
  
  <div class="login-container">
    <Grid>
      <Row>
        <Column sm={4} md={8} lg={6} style="margin:auto;">
          <Form on:submit={handleLogin}>
            <h1 style="margin-bottom: 20px;">User Login</h1>
            <FormGroup legendText="Login Details" style=" margin-top:30px; margin-bottom:20px;">
              <TextInput labelText="Email address" placeholder="Enter your email address..." bind:value={email} required style="margin-bottom:20px;" />
              <PasswordInput labelText="Password" placeholder="Enter your password..." bind:value={password} required />
            </FormGroup>
            <Button type="submit">Login</Button>
          </Form>
        </Column>
      </Row>
    </Grid>
  </div>