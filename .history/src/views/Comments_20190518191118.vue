<template>
    <div class="wrapper">
    <Header />
    <main class="main">
        <h1>Comments</h1>
        <div class="comments-section" v-if="comments && comments.length">
            <div class="comment-item" v-for="(comment, id) in comments" :key="id">
                <h3>{{ comment.title }}</h3>
                <p>{{ comment.body }}</p>
                <button class="more"><router-link to="/comment">Read more</router-link></button>
            </div>
            <!--<div class="comment-item">
                <h3>Why do we use it?</h3>
                <p>Itis a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution.</p>
                <button class="more">Read more</button>
            </div>
            <div class="comment-item">
                <h3>Where does it come from?</h3>
                <p>Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source.</p>
                <button class="more">Read more</button>
            </div>
            <div class="comment-item">
                <h3>There are many variations of passages of Lorem Ipsum available.</h3>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</p>
                <button class="more">Read more</button>
            </div>
            <div class="comment-item">
                <h3>If you are going to use a passage</h3>
                <p>If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text.</p>
                <button class="more">Read more</button>
            </div>
            <div class="comment-item">
                <h3>What is Lorem Ipsum?</h3>
                <p>There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable.</p>
                <button class="more">Read more</button>
            </div>-->
        </div>
        <h2>Lorem Ipsum is text of the typesetting industry</h2>
        <button class="backhome"><router-link to="/">Back to homepage</router-link></button>
    </main>
    <footer class="footer comments-footer">
     <hr>
     <div class="contacts">
       <div class="email-phone">
         <p><a href="mailto:mail@mailtest.com">mail@mailtest.com</a></p>
        <p><a href="tel:+30-6977664062">+30-6977664062</a></p> 
       </div>
       <div class="copyright">
       Copyright © 2019 Test All Rights Reserved.
     </div>
     </div>
   </footer>
    </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue';
import axios from 'axios'

export default {
  name: 'comments',
  components: {
    Header
  },

  data: () => ({
    comments: [],
    errors: []
  }),
  created() {
    axios.get('https://5cbef81d06a6810014c66193.mockapi.io/api/comments')
    .then(response => {
      this.comments = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
.wrapper {
  width: 100%;
  max-width: 1366px;
  margin: auto;
  background-color: #ffffff;
}
h1 {
    color: #111518;
    font-family: "SofiaPro", sans-serif;
    font-size: 70px;
    font-weight: 600;
    line-height: 72px;
    padding-left: 183px;
    margin-bottom: 99px;
}
.comments-section {
    width: 100%;
    max-width: 1006px;
    margin: auto;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    margin-bottom: 120px;
}
.footer.comments-footer {
    height: auto;
    padding: 0 50px 0 50px;
}
.comment-item {
    padding: 44px 49px 0 30px;
    box-shadow: 7px 11px 30px rgba(17, 21, 24, 0.04);
    border-radius: 3px;
    background-color: #ffffff;
    width: 483px;
    height: fit-content;
}
.comment-item h3 {
    margin: 0;
}
button.more {
    margin-bottom: 45px;
}

button.more a 
.main h2 {
    opacity: 0.5;
    color: #111518;
    font-family: "SofiaPro", sans-serif;
    font-size: 24px;
    font-weight: 600;
    line-height: 72px;
    margin: auto;
    margin-bottom: 39px;
}
button.backhome {
    width: 212px;
    height: 55px;
    border-radius: 3px;
    border: 1px solid #60e3a1;
    background-color: transparent;
    margin: auto;
    margin-bottom: 100px;
    position: relative;
    padding-left: 25px;
}
button.backhome a {
    color: #1d1e25;
    font-family: "SofiaPro", sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 53px;
    text-decoration: none;
}
button.backhome:hover {
    background-color: #60e3a1;
}
button.backhome::before {
    width: 10px;
    height: 12px;
    position: absolute;
    top: 22px;
    left: 22px;
    content: "";
    background-image: url('../assets/arrow.png');
}
.main {
    display: flex;
    flex-direction: column;
}
</style>
