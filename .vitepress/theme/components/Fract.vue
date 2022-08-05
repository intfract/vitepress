<temlpate>
  
</temlpate>

<script setup>
  import { onMounted } from 'vue';
  onMounted(() => {
    const name = document.querySelector('.VPNavBarTitle .text')
    const logo = document.querySelector('.VPNavBarTitle .logo')
    name.innerHTML = 'Defract'
    logo.innerHTML = ''
  })
</script>