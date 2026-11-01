<template>
  <main>
    <h1>Image server is running</h1>
    <p>Place image files in the <code>public</code> folder.</p>
    <p>For example, <code>public/qrcode1.png</code> is available at:</p>
    <p><a href="/qrcode1.png" target="_blank" rel="noreferrer">/qrcode1.png</a></p>
  </main>
</template>

<style scoped>
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
</style>
