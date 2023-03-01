<template>
    <main-layout>
      <div>
        <button @click="sendMqttMessage">Enviar mensagem MQTT</button><br>
        <input v-model="mqttMessage" type="text" placeholder="Digite a mensagem a ser enviada">
      </div>
    </main-layout>
  </template>
  
  <script>
    import MainLayout from '../layouts/Main.vue'
    import VueMqtt from 'vue-mqtt';
  
    export default {
      name: 'MyComponent',
      components: {
        MainLayout
      },
      data() {
        return {
          mqttConnected: false,
          mqttError: false,
          mqttMessage: ''
        }
      },
      mounted() {
        // Configurar a conexão MQTT
        Vue.use(VueMqtt, 'broker.mqttdashboard.com');
  
        // Verificar o status da conexão MQTT
        this.$mqtt.subscribe('testtopic/65854');
        this.$mqtt.on('connect', () => {
          this.mqttConnected = true;
          console.log('Conectado ao servidor MQTT');
        });
        this.$mqtt.on('error', () => {
          this.mqttError = true;
          console.log('Erro ao se conectar ao servidor MQTT');
        });
      },
      methods: {
        sendMqttMessage() {
          if (this.mqttConnected) {
            this.$mqtt.publish('testtopic/65854', this.mqttMessage);
            console.log('Mensagem MQTT enviada:', this.mqttMessage);
          } else {
            console.log('Não é possível enviar mensagem MQTT, não conectado ao servidor');
          }
        }
      }
    }
  </script>
  