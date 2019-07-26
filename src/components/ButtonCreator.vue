<template>
  <div class="hello">

    <h1>Vue Button Creator</h1>
    <h3>Edit the button to your liking</h3>
    <h2>Then copy the CSS snippet to your project</h2>

    <div class="container">

      <div class="main-btn">
          <button id="styled-btn" type="button" name="button" v-bind:style="styleObject">{{ message }}</button>
      </div>

      <div class="inputs">
        <div class="input-group">
          <label for="backgroundColor">Background-color:</label>
          <input id="backgroundColor" type="text" name="" v-model="styleObject.backgroundColor">
        </div>

        <div class="input-group">
          <label for="color">Color:</label>
          <input id="color" type="text" name="" v-model="styleObject.color">
        </div>

        <div class="input-group">
          <label for="borderRadius">Border-radius:</label>
          <input id="borderRadius" type="text" name="" v-model="styleObject.borderRadius">
        </div>

        <div class="input-group">
          <label for="height">Height:</label>
          <input id="height" type="text" name="" v-model="styleObject.height">
        </div>

        <div class="input-group">
          <label for="width">Width:</label>
          <input id="width" type="text" name="" v-model="styleObject.width">
        </div>

        <div class="input-group">
          <label for="fontSize">Font-size:</label>
          <input id="fontSize" type="text" name="" v-model="styleObject.fontSize">
        </div>

        <div class="input-group">
          <label for="boxShadow">Box-shadow:</label>
          <input id="boxShadow" type="text" name="" v-model="styleObject.boxShadow">
        </div>
      </div>
    </div> <!-- /containter -->

    <div class="working-btns">
      <button v-on:click="showCodeSnippet" class="getCode-btn" type="button" name="button">Get CSS code</button>
      <button v-on:click="resetStyles" class="reset-btn" type="button" name="button">Reset</button>
    </div>

    <hr>

    <div v-if="showCode" class="css-code">
      <h2>CSS Code</h2>
      <code>
        .btn { <br>
          <div class="indented-code">
            background-color: {{styleObject.backgroundColor}}; <br>
            color: {{styleObject.color}}; <br>
            border-radius: {{styleObject.borderRadius}}; <br>
            height: {{styleObject.height}}; <br>
            width: {{styleObject.width}}; <br>
            font-size: {{styleObject.fontSize}}; <br>
            box-shadow: {{styleObject.boxShadow}}; <br>
          </div>
        }
      </code>
    </div>

    <hr>

    <p>&copy; Copyright 2019 - Claudio Rescigno</p>

  </div>
</template>

<script>
export default {
  name: 'ButtonCreator',

  data() {
    return {
      showCode: false,
      message: 'Click me',
      styleObject: {
        backgroundColor: '#00c081',
        color: '#304860',
        borderRadius: '1px',
        height: '100px',
        width: '200px',
        fontSize: '2rem',
        boxShadow: '3px 3px 5px #333',
        cursor: 'pointer',
      }
    }
  },
  methods: {
    resetStyles() {
      this.styleObject.backgroundColor = '#00c081'
      this.styleObject.color = '#304860'
      this.styleObject.borderRadius = '1px'
      this.styleObject.height = '100px'
      this.styleObject.width = '200px'
      this.styleObject.fontSize = '2rem'
      this.styleObject.boxShadow = '3px 3px 5px #333'
      this.showCode = false
      this.message = 'Click me'
    },
    showCodeSnippet() {
      this.showCode = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  hr {
    width: 60%;
    margin: 50px auto;
  }

  .container {
    /* border: 2px solid red; */
    padding: 0;
    max-width: 70%;
    margin: auto;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }

  .main-btn {
    margin: 2rem auto;
  }

  .inputs {
    marign: 0 auto;
    border: 1px solid #eee;
    padding: 5px;
    /* width: 400px; */
    display: flex;
    flex-direction: column;
    align-items:flex-end;
  }

  .input-group {
    margin: 10px;
  }

  label {
    margin-right: 5px;
    font-size: 1.2rem;
  }

  input {
    padding: 5px;
    height: 1.5rem;
    font-size: 1rem;
  }

  .working-btns {
    align-self: center;
    margin-top: 30px;
  }

  .working-btns button {
    display: block;
    margin: 20px auto;
    color: white;
    padding: 8px;
  }

  .reset-btn {
    background-color: red;
    font-size: 1rem;
    border-radius: 3px;
    cursor: pointer;
  }
    .getCode-btn {
      background-color: #00c081;
      height: 50px;
      width: 200px;
      font-size: 1.4rem;
      border-radius: 3px;
      cursor: pointer;
    }

  .css-code {
    margin: auto;
    width: 290px;
    text-align: left;
  }

  code {
    font-size: 1.1rem;
  }

  .indented-code {
    margin-left: 20px;
  }
</style>
