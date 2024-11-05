<template>
  <div>
    <h2></h2>
    <textarea v-model="userInput" placeholder="Escribe tu pregunta"></textarea>
    <button @click="fetchResponse">Enviar</button>
    <div v-if="response">
      <p>Respuesta: {{ response }}</p>
    </div>
  </div>
</template>
<script>
import axios from 'axios';
export default {
  data() {
    return {
      userInput: '',
      response: null,
    };
  },
  methods: {
    async fetchResponse(){
        try{
        const result  = await axios.post('https://api.openai.com/v1/chat/completions',{
            model:"gpt-4",
            messages:[{role:"user", content: this.userInput}],
            max_tokens: 150,

        },
        {
            headers: {
             'Content-Type': 'application/json',
             'Authorization': ``,
            },   
        }
    );
    this.response = result.data.choices[0].message.content;
    } 
    catch (error) {
    console.error('Error al obtener la respuesta:', error);
  }    
}
}
}
</script>