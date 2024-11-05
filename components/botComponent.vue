<template>
    <div class="row text-white bg-dark bg-gradient">
        <div class="col-md-4 mx-auto text-gray-600">
            <div class="form-group">
                <input type="text" class="form-control" placeholder="Pregunta algo ?">
                <button class="btn btn-lg w-100 p-1 btn-success rounded" >Enviar</button>
                <div>
                    <p>Respuesta: {{ }}</p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import { axios } from 'axios'

export default ({
    async: true,
})
</script>
