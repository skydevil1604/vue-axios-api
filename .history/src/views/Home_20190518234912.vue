<template>
  <div class="wrapper">
   <Header />
   <main class="main">
     <div class="main-text">
       <h1>{{comment.title}}</h1>
     </div>
     <div class="main-photo">
       <img src="../assets/office_photo.png" alt="">
     </div>
     <div class="info-block">
       <div class="info-text">
         <div class="info-text-item first-item">
          <h3>Who we are</h3>
          <ul>
            <li>It is a long established fact that a reader will be distracted</li>
            <li>The readable content of a page when looking at its layout</li>
            <li>The point of using Lorem Ipsum</li>
            <li>As opposed to using 'Content here, content here'.</li>
          </ul>
         </div>
         <div class="info-text-item second-item">
          <h3>What we do</h3>
          <ul>
            <li>Many desktop publishing packages and web page</li>
            <li>There are many variations of passages of Lorem Ipsum available, but the majority have</li>
            <li>Various versions have evolved over the years, sometimes by accident.</li>
          </ul>
         </div>
         <div class="info-text-item third-item">
          <h3>Technology</h3>
          <ul>
            <li>The point of using Lorem Ipsum</li>
            <li>As opposed to using 'Content here, content here'</li>
            <li>Contrary to popular belief, Lorem Ipsum is not simply random text</li>
            <li>A Latin professor at Hampden-Sydney College in Virginia</li>
          </ul>
         </div>
       </div>
     </div>
   </main>
   <footer class="footer">
     <div id="write-comment">
       <h2>Write comment</h2>
       <div class="main-form">
         <form action="#" method="post">
           <input type="text" v-model="title" placeholder="Title">
           <input type="textarea" v-model="body" placeholder="Your comment">
           <button type="submit" @click="console()>Send</button>
         </form>
       </div>
     </div>
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
import axios from 'axios';
import Header from '@/components/Header.vue';

export default {
  name: 'home',
  components: {
    Header
  },
  data: () => ({
    comment: [],
    errors: [],
    title: '',
    body: ''
  }),

  methods: {
    commentPost() {
      axios.post('https://5cbef81d06a6810014c66193.mockapi.io/api/comments', 
        this.title, this.body,
        { headers: {
          'Content-type': 'application/json',
        }
      })
      .then(response => {})
      .catch(e => {
        this.errors.push(e),
        alert('Thank you for your comment!')
      })
    }
  },

  created() {
    axios.get('https://5cbef81d06a6810014c66193.mockapi.io/api/comments/50')
    .then(response => {
      this.comment = response.data
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
.main-text {
  width: 100%;
  max-width: 1366px;
  box-sizing: border-box;
  padding: 0 343px 0 182px;
  margin-bottom: 74px;
}
.main-text h1 {
  margin: 0;
  width: 100%;
  max-width: 841px;
  color: #111518;
  font-size: 69px;
  font-weight: 600;
  line-height: 72px;
}
.main-photo {
  width: 100%;
  max-width: 1366px;
}
.main-photo img {
  width: 100%;
}
.info-block {
  background-color: #f7f7f7;
  width: 100%;
  max-width: 1366px;
  padding-top: 114px;
  display: flex;
}
.info-text {
  margin: auto;
  display: flex;
  justify-content: space-between;
  margin-bottom: 119px;
  width: 100%;
  max-width: 1002px;
}
.info-text-item ul {
  margin: 0;
  padding: 0;
  padding-left: 20px;
}
.info-text-item ul li {
  padding-bottom: 20px;
}
.info-text-item ul li:last-child {
  padding-bottom: 0;
}
.info-text-item {
  color: #101417;
  font-family: "SofiaPro";
  font-size: 16px;
  font-weight: 400;
}
.info-text-item h3 {
  color: #101417;
  font-family: "SofiaPro";
  font-size: 36px;
  font-weight: 700;
  line-height: 80px;
}
.first-item {
  width: 253px;
  position: relative;
}
.second-item {
  width: 231px;
  position: relative;
}
.third-item {
  width: 254px;
  position: relative;
}
.first-item h3::before {
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  background-image: url('../assets/users-icon.png');
  width: 40px;
  height: 29px;
}
.second-item h3::before {
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  background-image: url('../assets/comp_icon.png');
  width: 40px;
  height: 34px;
}
.third-item h3::before {
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  background-image: url('../assets/detail_icon.png');
  width: 36px;
  height: 37px;
}
footer.footer {
  padding: 140px 50px 0 50px;
  width: 100%;
  max-width: 1366px;
  background-color: #1d1e25;
  height: 678px;
}
#write-comment {
  width: 100%;
  max-width: 1008px;
  margin: 0 auto 0 auto;
  display: flex;
  justify-content: space-between;
  margin-bottom: 145px;
}
#write-comment h2 {
  color: #ffffff;
  font-family: "SofiaPro", sans-serif;
  font-size: 55px;
  font-weight: 700;
  line-height: 50px;
  width: 234px;
  margin: 0;
  position: relative;
}
#write-comment h2::after {
  content: "";
  position: absolute;
  width: 70px;
  height: 5px;
  background-color: #f9d10d;
  left: 0;
  bottom: 139px;
}
.main-form {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
  max-width: 592px;
}
.main-form input {
  border-radius: 3px;
  border: 1px solid #60e3a1;
  width: 100%;
  max-width: 592px;
  background-color: transparent;
  opacity: 0.6;
  color: #60e3a1;
  font-family: "SofiaPro", sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 31px;
  padding-left: 20px;
  outline: none;
}
.main-form input:focus {
  border: 1px solid #60e3a1;
}
.main-form input:active {
  border: 1px solid #60e3a1;
}
.main-form input[type=textarea] {
  height: 150px;
  margin-bottom: 15px;
}
.main-form input[type=text] {
  height: 55px;
  margin-bottom: 15px;
}
button {
  width: 150px;
  height: 55px;
  border-radius: 3px;
  background-color: #60e3a1;
  color: #1d1e25;
  font-family: "SofiaPro", sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 53px;
  border: 1px solid #60e3a1;
}
.main-form input::placeholder {
  opacity: 0.6;
  color: #60e3a1;
  font-family: "SofiaPro", sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 31px;
}
hr {
  opacity: 0.1;
}
.contacts {
  display: flex;
  justify-content: space-between;
}
.email-phone p {
  margin: 0;
}
.email-phone p a {
  text-decoration: none;
  color: #ffffff;
  font-family: "SofiaPro", sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
}
.email-phone {
  margin-bottom: 30px;
  padding-top: 10px;
}
.copyright {
  color: #4a4d5e;
  font-family: "SofiaPro", sans-serif;
  font-size: 13px;
  font-weight: 400;
  line-height: 26px;
  align-self: center;
  margin-top: -20px;
}
</style>

