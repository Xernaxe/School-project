<template>
  <header>
    <nav class="nav">
      <div class="navWrapper">
        <ul class="navUL">
          <li v-for="item in orderedNavItems" :key="item.text">
            <div class="navDiv" v-if="item.active">
              <p class="navLogo">Jan'S</p>
              <routerLink :to="item.path" class="navLink">
                <div class="transitionWrapper">
                  <div class="lettersWrapper">
                    <template v-for="(letter, index) in item.letters" :key='index'>
                      <span 
                      class="navLetter active coloredSpan"
                      :style="{ transitionDelay: (index * 0.1) + 's' }"
                      >{{ letter }}</span>
                    </template>
                  </div>
                  <div class="lettersWrapper">
                    <template v-for="(letter, index) in item.letters" :key='index'>
                      <span 
                      class="navLetter active whiteSpan"
                      :style="{ transitionDelay: (index * 0.1) + 's' }"
                      >{{ letter }}</span>
                    </template>
                  </div>
                </div>
              </routerLink>

            </div>
            <routerLink
              v-else
              :to="item.path"
              class="navLink"
              >
              <div class="transitionWrapper">
                  <div class="lettersWrapper">
                    <template v-for="(letter, index) in item.letters" :key='index'>
                      <span 
                      class="navLetter"
                      :style="{ transitionDelay: (index * 0.1) + 's' }"
                      >{{ letter }}</span>
                    </template>
                  </div>
                  <div class="lettersWrapper">
                    <template v-for="(letter, index) in item.letters" :key='index'>
                      <span 
                      class="navLetter coloredSpan"
                      :style="{ transitionDelay: (index * 0.1) + 's' }"
                      >{{ letter }}</span>
                    </template>
                  </div>
                </div>
              </routerLink
            >
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navItems: [
        { text: "Home", path: "/", active: true, letters: ['H','o','m','e']},
        { text: "Music", path: "/music", letters: ['M','u','s','i','c'] },
        { text: "Story", path: "/story", letters: ['S','t','o','r','y'] },
        { text: "Lessons", path: "/lessons", letters: ['L','e','s','s','o','n','s'] },
        { text: "Contact", path: "/contact", letters: ['C','o','n','t','a','c','t'] },
      ],
      navItemsCopy: [],
      lettersArr: []
    };
  },
  computed: {
    orderedNavItems() {
      switch (this.$route.name) {
        case "story":
          this.navItems = [
            { text: "Story", path: "/story", active: true , letters: ['S','t','o','r','y']},
            { text: "Home", path: "/" , letters: ['H','o','m','e']},
            { text: "Music", path: "/music", letters: ['M','u','s','i','c']  },
            { text: "Lessons", path: "/lessons", letters: ['L','e','s','s','o','n','s'] },
            { text: "Contact", path: "/contact", letters: ['C','o','n','t','a','c','t'] },
          ];
          break;

        case "home":
          this.navItems = [
          { text: "Home", path: "/", active: true , letters: ['H','o','m','e']},
          { text: "Music", path: "/music",  letters: ['M','u','s','i','c']   },
          { text: "Story", path: "/story", letters: ['S','t','o','r','y'] },
          { text: "Lessons", path: "/lessons", letters: ['L','e','s','s','o','n','s'] },
          { text: "Contact", path: "/contact", letters: ['C','o','n','t','a','c','t'] },
          ];
          break;
        case "contact":
          this.navItems = [
            { text: "Contact", path: "/contact", active: true, letters: ['C','o','n','t','a','c','t'] },
            { text: "Home", path: "/", letters: ['H','o','m','e'] },
            { text: "Music", path: "/music",  letters: ['M','u','s','i','c'] },
            { text: "Story", path: "/story" , letters: ['S','t','o','r','y']},
            { text: "Lessons", path: "/lessons", letters: ['L','e','s','s','o','n','s'] },
          ];
          break;
        case "music":
          this.navItems = [
            { text: "Music", path: "/music", active: true,  letters: ['M','u','s','i','c'] },
            { text: "Home", path: "/", letters: ['H','o','m','e'] },
            { text: "Story", path: "/story", letters: ['S','t','o','r','y']},
            { text: "Lessons", path: "/lessons", letters: ['L','e','s','s','o','n','s'] },
            { text: "Contact", path: "/contact", letters: ['C','o','n','t','a','c','t'] },
          ];
          break;
        case "lessons":
          this.navItems = [
            { text: "Lessons", path: "/lessons", active: true, letters: ['L','e','s','s','o','n','s'] },
            { text: "Home", path: "/", letters: ['H','o','m','e'] },
            { text: "Music", path: "/music",  letters: ['M','u','s','i','c'] },
            { text: "Story", path: "/story", letters: ['S','t','o','r','y']},
            { text: "Contact", path: "/contact", letters: ['C','o','n','t','a','c','t'] },
          ];
          break;
      }
      this.navItemsCopy = this.navItems
      return this.navItemsCopy;
    }
  }
};
</script>

<style scoped>

@media (max-width: 850px){
  header{
    display: none;
  }
}
.whiteSpan{
  color: white !important;
}
.coloredSpan{
  color: #9D9171;
}
.active{
  font-size: 40px!important;
}
.transitionWrapper{
  display: flex;
  flex-direction: column;
  gap: 20px;
  position: absolute;
  top: 0;
}
.lettersWrapper{
  display: flex;
  height: min-content;
}
.navLink {
  display: inline-block;
  position: relative;
  overflow: hidden;
  width: 131px;
  height: 35px;
  /* transform: translateY(-10px); */
}

.navLetter {
  display: inline-block;
  position: relative;
  font-size: 20px;
  transition: all 0.5s ease-in-out;
  line-height: 30px;
  height: min-content;
}

.navLink:hover .navLetter {
  transform: translateY(-50px);

}

.navDiv {
  display: flex;
  align-items: center;
  position: relative;
}

.navLogo {
  font-size: 30px;
  position: absolute;
  left: -80px;
}

.navWrapper {
  display: flex;
  align-items: center;
  height: 100px;
  margin-left: 10vw;
}

.navUL {
  width: 100vw;
  display: flex;
  justify-content: space-evenly;
}

.router-link-active {
  font-size: 40px;
  font-weight: lighter;
  color: #9D9171;
}
</style>
