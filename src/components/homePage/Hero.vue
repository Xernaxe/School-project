<template>
  <section class="heroSection">
    <div class="heroWrapperLeft">
      <img class="heroImg" :src="photoSrc" alt="Photo of me" />
    </div>
    <div class="heroWrapperRight">
      <div class="heroInWrapper">
        <h1 class="heroHeader"><span class="spanColor">Jan</span>’<span class="spanColor">Sedlák</span></h1>
        <p class="heroP">
          I am <span class="spanColor">bass player</span>, <span class="spanColor">band leader</span> and also a <span class="spanColor">teacher</span>. Welcome to my portfolio and get to know me better!
        </p>
        <p class="heroP">
          “To me, there is great power in connecting people. I believe that
          through music, we can communicate regardless language barriers. Let
          music help us find a way to each other."
        </p>
        <div class="socialsWrapper">
          <a href="https://www.facebook.com/JanSedlakMusic" target="_blank">
            <img class="socialsImg" src="/facebook.svg" alt="Facebook">
            <label for="socials">Facebook</label>
          </a>
          <a href="https://www.instagram.com/jansedlakmusic/" target="_blank">
            <img class="socialsImg" src="/instagram.svg" alt="Instagram" >
            <label for="socials">Instagram</label>
          </a>
          <a href="https://www.youtube.com/channel/UC_9pTBpqYj7uC65ENli4fBg" target="_blank">
            <img class="socialsImg" src="/youtube.svg" alt="Youtube" style="width:42px">
            <label for="socials">Youtube</label>
          </a>
          <a href="https://open.spotify.com/artist/6eslWoqLqMP35uERDUwFQO?si=FYTk6g7BQDGLhHeBzvB9FQ" target="_blank">
            <img class="socialsImg" src="/spotify.svg" alt="Spotify">
            <label for="socials">Spotify</label>
          </a>
          <a href="https://music.apple.com/tm/artist/jan-sedlak/519939094" target="_blank">
            <img class="socialsImg" src="/applemusic.svg" alt="AppleMusic" />
            <label for="socials">Apple music</label>
          </a>
          <a href="https://jansedlakmusic.bandcamp.com/" target="_blank">
            <img class="socialsImg" src="/bandcampNew.svg" alt="Bandcamp" style="width:30px">
            <label for="socials" style="display: flex; gap: 5px;">Bandcamp
              <img src="/shop.svg" alt="shop" style="width:9px">
            </label>
          </a>
        </div>
        <div class="contact">
          <a href="mailto:contact@jansedlakmusic.com" target="_blank" class="contactWrapper">
            <div class="iconWrapper">
              <img src="/mailIcon.svg" alt="Mail Icon">
            </div>
            <p class="locationP">contact@jansedlakmusic.com</p>
          </a>
          <a href="tel:+45 42 31 43 34" target="_blank" class="contactWrapper">
            <div class="iconWrapper">
              <img src="/phoneIcon.svg" alt="Phone Icon">
            </div>
            <p class="phoneNrP">+45 42 31 43 34</p>
          </a>
          <a href="https://goo.gl/maps/ZyraNidTe1Wg3FYt9" class="contactWrapper" target="_blank">
            <div class="iconWrapper">
              <img src="/locationIcon.svg" alt="Location Icon">
            </div>
            <p class="locationP">Aalborg 9000, Denmark</p>
          </a>
    </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props:{
    photoSrc:{
      type: String,
    }
  }
};
</script>

<style scoped>
.iconWrapper{
  width: 30px;
}

.contactWrapper{
  display: flex;
  align-items: flex-end;
  gap: 10px;
}

.contact{
  margin-top: 30px;
  width:fit-content;
  display: flex;
  flex-direction: column;
  gap: 10px;
  /* margin-left: 10vw; */
}
.spanColor{
  color: #9D9171;
}

.socialsWrapper > a{
    display: flex;
    flex-direction: column;
    gap: 5px;
    align-items: center;
  }

.socialsWrapper label {
  font-size: 10px;
}

.heroImg {
  width: fit-content;
  height: fit-content;
  border-radius: 15px;
}

.heroSection {
  display: flex;
  align-items: flex-end;
  gap: 20px;
  justify-content: center;
  flex-direction: row;
}

.heroWrapperRight {
  width: 440px;
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.heroHeader {
  font-size: 2.5rem;
}

.socialsWrapper a, .contact a {
  transition: all 0.3s ease-in-out;
}

.socialsWrapper a:hover, .contact a:hover {
  transform: scale(1.1);
  cursor: pointer;
}

.socialsWrapper{
  display: flex;
  gap: 30px;
  align-items: flex-end;
}

.socialsImg {
  width: 28px;
}

.heroP {
  margin: 10px 0 30px;
}

@media only screen and (max-width: 970px) {
  .heroSection {
    flex-direction: column;
    align-items: center;
  }

.heroHeader {
  text-align: center;
}

.contact {
  margin: 50px auto 0 auto;
}
}

@media (max-width: 420px){
  .socialsWrapper{
    gap: 10px;
    width: 45vw;
    margin: auto;
  }

  .socialsWrapper > a{
    width: 52px;
  }

  .heroP{
    text-align: center;
  }
}

@media only screen and (max-width: 490px) {
  .heroImg {
    width: 90vw;
    align-self: center;
  }

  .heroWrapperRight {
    width: 90vw;
  }

  .socialsWrapper {
    flex-wrap: wrap;
    justify-content: center;
  }
}
</style>
