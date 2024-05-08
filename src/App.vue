<script setup>
import { RouterLink, RouterView } from 'vue-router'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap'
import Form from './components/Form.vue'
import Card from './components/Card.vue'
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="card">
        <Form />
      </div>
    </div>
    <div class="row">
      <div class="card">
        <Card />
      </div>
    </div>
  </div>
</template>
