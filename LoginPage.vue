<template>
  <div class="login-container">
    <div class="login-content">
      <!-- Left side - Image (desktop only) -->
      <div class="image-section">
        <div class="logo-section">
          <div class="logo">
            <img src="./logo.png" alt="Team Achieve Logo" />
          </div>
        </div>
        <div class="hero-image">
          <img src="./hero.png" alt="Team collaboration" class="hero-img" />
        </div>
        <div class="brand-footer">
          <h3>Team Achieve</h3>
          <p>Your perfect solution for funding your desires</p>
        </div>
      </div>

      <!-- Right side - Login Form -->
      <div class="form-section">
        <div class="mobile-logo">
          <div class="logo">
            <img src="./logo.png" alt="Team Achieve Logo" />
          </div>
        </div>

        <div class="form-container">
          <h1 class="welcome-title">Welcome Back</h1>
          <p class="welcome-subtitle">Enter your email address and password to access your account.</p>

          <form @submit.prevent="handleLogin" class="login-form">
            <div class="form-group">
              <label for="email" class="form-label">
                Email Address <span class="required">*</span>
              </label>
              <input
                id="email"
                v-model="email"
                type="email"
                placeholder="Enter your email"
                class="form-input"
                required
              />
            </div>

            <div class="form-group">
              <label for="password" class="form-label">
                Password <span class="required">*</span>
              </label>
              <div class="password-input-container">
                <input
                  id="password"
                  v-model="password"
                  :type="showPassword ? 'text' : 'password'"
                  placeholder="Enter your password"
                  class="form-input password-input"
                  required
                />
                <button
                  type="button"
                  @click="togglePassword"
                  class="password-toggle"
                >
                  <img src="./eye.svg" alt="Toggle password visibility" width="20" height="20" />
                </button>
              </div>
            </div>

            <div class="form-options">
              <label class="checkbox-container">
                <input v-model="rememberMe" type="checkbox" class="checkbox" />
                <span class="checkmark"></span>
                Remember me
              </label>
              <a href="#" class="forgot-password">Forgot Password?</a>
            </div>

            <button type="submit" class="sign-in-btn">Sign in</button>

            <p class="signup-link">
              Don't have an account? <a href="#" class="signup-text">Sign up</a>
            </p>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  data() {
    return {
      email: '',
      password: '',
      rememberMe: false,
      showPassword: false
    }
  },
  methods: {
    handleLogin() {
      console.log('Login attempt:', {
        email: this.email,
        password: this.password,
        rememberMe: this.rememberMe
      })
    },
    togglePassword() {
      this.showPassword = !this.showPassword
    }
  }
}
</script>

<style scoped>
.login-container {
  min-height: 100vh;
  display: flex;
}

.login-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  width: 100%;
  min-height: 100vh;
}

.image-section {
  background: #F8EAFF;
  padding: 40px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  position: relative;
}

.logo-section {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo img {
  width: 198px;
  height: 97px;
  object-fit: contain;
  margin-left: 20px;
}

.brand-name {
  font-size: 24px;
  font-weight: 600;
  color: #64748b;
  margin: 0;
}

.hero-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 40px 0;
}

.hero-img {
  width: 626px;
  height: 417px;
  border-radius: 15px;
  object-fit: cover;
}

.brand-footer h3 {
  font-size: 28px;
  font-weight: 700;
  color: #61227D;
  margin: 0 0 8px 0;
  text-align: center;
}

.brand-footer p {
  color: #64748b;
  font-size: 16px;
  margin: 0;
  text-align: center;
}

.form-section {
  padding: 40px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.mobile-logo {
  display: none;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin-bottom: 40px;
}

.form-container {
  max-width: 400px;
  margin: 0 auto;
  width: 100%;
}

.welcome-title {
  font-size: 32px;
  font-weight: 700;
  color: #61227D;
  margin: 0 auto 12px auto;
  text-align: center;
  width: fit-content;
}

.welcome-subtitle {
  color: #64748b;
  font-size: 16px;
  margin: 0 auto 32px auto;
  
  line-height: 1.5;
  width: 477px;
  height: 24px;
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.form-label {
  font-size: 14px;
  font-weight: 500;
  color: #374151;
  text-align: left;
}

.required {
  color: #ef4444;
}

.form-input {
  padding: 12px 16px;
  border: 2px solid #e5e7eb;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.2s;
}

.form-input:focus {
  outline: none;
  border-color: #61227D;
}

.password-input-container {
  position: relative;
}

.password-input {
  width: 100%;
}

.password-toggle {
  position: absolute;
  right: 2px;
  top: 2px;
  bottom: 2px;
  background: #F7F7F7;
  border: none;
  color: #6b7280;
  cursor: pointer;
  padding: 8px;
  border-radius: 0 6px 6px 0;
  display: flex;
  align-items: center;
}

.form-options {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 8px 0;
  text-align: left;
}

.checkbox-container {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 14px;
  color: #374151;
  cursor: pointer;
  text-align: left;
}

.checkbox {
  width: 16px;
  height: 16px;
  accent-color: #61227D;
}

.forgot-password {
  color: #61227D;
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
}

.forgot-password:hover {
  text-decoration: underline;
}

.sign-in-btn {
  background: #61227D;
  color: white;
  border: none;
  padding: 14px;
  border-radius: 8px;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: background-color 0.2s;
  margin-top: 8px;
}

.sign-in-btn:hover {
  background: #4a1a5f;
}

.signup-link {
  text-align: center;
  color: #6b7280;
  font-size: 14px;
  margin: 16px 0 0 0;
}

.signup-text {
  color: #61227D;
  text-decoration: none;
  font-weight: 500;
}

.signup-text:hover {
  text-decoration: underline;
}

/* Mobile Styles */
@media (max-width: 768px) {
  .login-content {
    grid-template-columns: 1fr;
  }

  .image-section {
    display: none;
  }

  .mobile-logo {
    display: flex;
  }

  .form-section {
    padding: 20px;
    justify-content: flex-start;
    padding-top: 60px;
  }

  .welcome-title {
    font-size: 28px;
  }

  .welcome-subtitle {
    font-size: 14px;
    margin-bottom: 24px;
  }

  .form-container {
    max-width: none;
  }

  .form-options {
    flex-direction: column;
    align-items: flex-start;
    gap: 12px;
  }

  .forgot-password {
    align-self: flex-end;
  }
}

@media (max-width: 480px) {
  .form-section {
    padding: 16px;
    padding-top: 40px;
  }

  .welcome-title {
    font-size: 24px;
  }

  .mobile-logo .brand-name {
    font-size: 20px;
  }

  .mobile-logo .logo svg {
    width: 40px;
    height: 40px;
  }
}
</style>