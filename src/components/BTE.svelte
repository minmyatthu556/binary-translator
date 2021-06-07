<script>
  import Card from '../shared/Card.svelte';
  import { scale } from 'svelte/transition';
  import { data } from '../data';

  let value = '';
  let converted = '';

  const handleTranslate = () => {
    let convertedArray = [];
    const textArray = value.split(' ');
    for (let i = 0; i < textArray.length; i++) {
      convertedArray.push(data[textArray[i]]);
    }
    converted = convertedArray.join('');
  };
</script>

<div in:scale|local>
  <Card>
    <h3>Input:</h3>
    <textarea
      name="binary"
      cols="30"
      rows="10"
      bind:value
      placeholder="Enter your binary code here"
    />
    <button class="button" on:click={handleTranslate}>translate</button>

    <h3>Output:</h3>
    <div class="output">{converted}</div>
  </Card>
</div>

<style>
  textarea {
    outline-color: #f2aa4cff;
  }

  .button {
    display: block;
    margin: auto;
    background-color: #f2aa4cff;
    color: #101820ff;
    outline: none;
    text-transform: uppercase;
    font-weight: bold;
    padding: 0.5em 1em;
    border-radius: 0.5em;
    letter-spacing: 0.04em;
  }

  .button:hover {
    background-color: rgb(238, 166, 71);
  }

  .button:active {
    background-color: rgb(255, 180, 82);
  }

  .output {
    max-width: 300px;
  }
</style>
