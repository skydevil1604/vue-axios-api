<template>
    <div class="wrapper">
    <Header />
    <main class="main">
   
        <div class="comment-section">
            <p class="backlink"><router-link to="/comments">Back to comments</router-link></p>
            <h1 class="main-head">Lorem Ipsum is simply dummy text of the printing and typesetting industry</h1>
            <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>
            <p>Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section.</p>
            <hr>
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

export default {
  name: 'comment',
  components: {
    Header
  }
}
</script>

<style>
.comment-section p:last-of-type {
    margin-bottom: 100px;
}
.comment-section hr {
    height: 1px;
    background-color: #4a4d5e;
    opacity: 0.1;
    margin-bottom: 100px;
}
h1.main-head {
    color: #101417;
    font-family: "SofiaPro", sans-serif;
    font-size: 48px;
    font-weight: 700;
    line-height: 50px;
    padding-left: 0;
    margin-bottom: 48px;
}
.footer.comments-footer {
    height: auto;
    padding: 0 50px 0 50px;
}
.comment-section {
    width: 100%;
    max-width: 765px;
    margin: auto;
}
p.backlink {
    padding-left: 20px;
    color: #1d1e25;
    font-family: "SofiaPro", sans-serif;
    font-size: 16px;
    font-weight: 400;
    line-height: 53px;
    text-decoration: underline;
    position: relative;
}
p.backlink::before {
    width: 10px;
    height: 12px;
    position: absolute;
    top: 22px;
    left: 0;
    content: "";
    background-image: url('../assets/arrow.png');
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
</style>
