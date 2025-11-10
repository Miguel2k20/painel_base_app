<template>
  <footer class="footer">
    <div class="container-fluid">
      <ul class="nav">
        <li class="nav-item">
          <a class="nav-link" href="https://github.com/Miguel2k20/" target="_blank">
            Github
          </a>
        </li>
      </ul>
      <div class="copyright">
        © {{ year }} — Feito com ❤️ por <strong>Miguel</strong>. Todos os direitos reservados.
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      year: new Date().getFullYear(),
    };
  },
};
</script>
<style></style>
