<script>
  import ThankYou from "./thankyou.svelte";
  import { fade } from "svelte/transition";
</script>

<svelte:head>
  <title>Contact</title>
</svelte:head>

<div in:fade={{ duration: 1000 }}>
  <h1>Contact Me</h1>
  <div class="container">
    <div id="envelope" class="envelope">
      <svg
        id="flap"
        class="flap"
        height="45%"
        width="100%"
        viewBox="0 0 100 100"
        preserveAspectRatio="none">
        <polygon points="0,0 100,0 50,100" />
      </svg>

      <form
        class="form"
        name="contact"
        method="POST"
        action="/thankyou"
        Content-Type="application/x-www-form-urlencoded"
        netlify
        netlify-honeypot="bot-field">
        <label for="form-name" id="form-name">
          <input type="hidden" name="form-name" value="contact" />
        </label>
        <label for="first-name" id="first-name">
          First Name
          <input
            class="text"
            type="text"
            name="first-name"
            placeholder="First Name"
            required />
        </label>
        <label for="last-name" id="last-name">
          Last Name
          <input
            class="text"
            type="text"
            name="last-name"
            placeholder="Last Name"
            required />
        </label>
        <label for="email" id="email">
          Email
          <input
            class="text"
            type="email"
            name="email"
            placeholder="Email"
            required />
        </label>
        <label for="subject" id="subject">
          Subject
          <input
            class="text"
            type="text"
            name="subject"
            placeholder="Subject" />
        </label>
        <label for="message" id="message">
          Message
          <textarea name="message" placeholder="Message" required />
        </label>
        <label for="submit" id="submit">
          <input type="submit" name="submit" value="Send" />
        </label>
      </form>
    </div>
    <div class="thanks">
      <a href="/thankyou">
        <ThankYou />
      </a>
    </div>
  </div>
</div>

<style>
  .thanks {
    display: none;
  }
  .container {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 75%;
    margin: 0 auto;
  }

  .envelope {
    margin-top: 0;
    position: relative;
    width: 40%;
    height: 500px;
    background: radial-gradient(#222, #111) 0 50%;

    display: grid;
    justify-items: center;
  }
  .flap {
    transition: 0.5s all linear;
    fill: whitesmoke;
    animation: open-flap 2s ease-in-out forwards;
    transform-origin: 0 0 0;
  }

  @supports (-ms-ime-align: auto) {
    .flap {
      height: 200px;
    }
  }

  .form {
    letter-spacing: 2px;
    position: absolute;
    top: -10px;
    width: 90%;
    height: 100%;
    display: grid;
    justify-content: stretch;
    align-content: flex-start;
    grid-gap: 1em;
    grid-template-columns: 1fr 1fr;
    margin: 0;
    padding: 0;
    font-size: 18px;
  }

  label {
    text-align: center;
    color: whitesmoke;
    font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
    font-style: italic;
    text-shadow: 2px 2px 2px rgba(36, 36, 36, 0.5),
      3px 3px 3px rgba(0, 0, 0, 0.8), 0px 0px 1px #111,
      #333 0.006em 0.006em 0.007em, #9c9c9c 1px 1px 1px;
  }

  input[placeholder],
  [placeholder],
  *[placeholder] {
    letter-spacing: 1.5px;
    color: rgb(0, 255, 255) !important;
  }

  textarea[placeholder] {
    letter-spacing: 1.5px;
    color: black !important;
  }

  ::-webkit-input-placeholder {
    /* Chrome/Opera/Safari */
    letter-spacing: 1.5px;
    color: rgb(0, 255, 255) !important;
  }

  textarea::-webkit-input-placeholder {
    letter-spacing: 1.5px;
    color: rgb(0, 0, 0) !important;
  }

  #first-name {
    grid-column: 1/1;
  }

  input[type="text"],
  input[type="email"] {
    color: white;
    font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
    font-weight: 500;
    border-radius: 5px;
    line-height: 18px;
    background-color: transparent;
    border: 2px solid #00cece;
    transition: all 0.3s;
    padding: 10px;
    margin: 0;
    width: 100%;
    box-sizing: border-box;
    outline: 0;
  }

  #email {
    grid-column: 1/-1;
  }

  #subject {
    grid-column: 1/-1;
  }

  #message {
    grid-column: 1/-1;
    display: grid;
  }

  textarea {
    border-radius: 5px;
    height: 100px;
    line-height: 125%;
    resize: vertical;
    margin: 0;
    vertical-align: top;
  }

  #submit {
    grid-column: 1/-1;
  }

  input[type="submit"] {
    font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;
    letter-spacing: 3px;
    font-size: 3vh;
    font-style: italic;
    color: rgb(255, 255, 255);
    text-shadow: 2px 2px 2px rgba(36, 36, 36, 0.5),
      3px 3px 3px rgba(0, 0, 0, 0.8), 0px 0px 1px #111,
      #333 0.006em 0.006em 0.007em, #9c9c9c 1px 1px 1px;
    width: 100%;
    background-color: rgb(1, 233, 233);
    border-radius: 5px;
    border: 1px solid transparent;
    cursor: pointer;
    padding: 10px 0;
    transition: all 0.2s ease-in;
  }

  input[type="submit"]:hover {
    background-color: #131313;
    border: 1px solid rgb(1, 233, 233);
  }

  @keyframes open-flap {
    0% {
      transform: rotateX(0deg);
    }
    50% {
      transform: rotateX(120deg);
      opacity: 1;
    }
    100% {
      transform: rotateX(0deg);
      opacity: 0.2;
    }
  }

  @media only screen and (max-width: 600px) {
    .envelope {
      width: 100%;
    }
  }

  @media only screen and (min-width: 601px) and (max-width: 1000px) {
    .envelope {
      width: 75%;
    }
  }

  @media only screen and (min-width: 1001px) and (max-width: 1400px) {
    .envelope {
      width: 70%;
    }
  }
</style>
