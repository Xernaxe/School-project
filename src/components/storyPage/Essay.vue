<template>
  <section class="Essay">
    <h2 class="sectionH">Reflections, essays and poetry</h2>
    <p class="essayP">“Once a while, I still enjoy writing. In 2020, I finished my first collection of poetry and once in a while, I enjoy reflecting on my creative process and on musicians’ life in general. Some of my texts are available here.”</p>
    <div class="essayEMB">
      <a style="display: flex;" href="https://drive.google.com/file/d/1ml1ui6XEnzH_dmKhXBdoKf7JVQoFDKaH/view?usp=share_link" target="_blank">Sunset-March-and-my-compositional-process
        <img src="/pdfIcon.svg" style="margin-left: 10px" alt="PDF">
      </a>
    </div>
  </section>
</template>

<script>
export default {
  
}

</script>

<style scoped>

.essayP{
  text-align: center;
  width: 750px;
  margin-bottom: 15px;
}

.essayEMB {
  transition: all .3s ease-in-out;
}

.essayEMB:hover {
  transform: scale(1.1);
}

a {
  text-decoration: underline;
}

@media only screen and (max-width: 376px) {
  .essayP{
    width: 257px;
  }
}

@media (max-width: 1023px){
  .essayP{
    width: 70vw;
  }
}
</style>