<template>
    <div class="card">
        <h3>{{card.titel}}</h3>
        <details>
            <summary>{{card.description}}</summary>
                <select v-model="cardstatus">
                    <option value="0" selected>Bevestiging verstuurd</option>
                    <option value="1">Product ligt klaar</option>
                    <option value="2">Product is verzonden</option>
                </select>
                <div @click="$emit('update-status', {'id': card.id, 'status' : cardstatus})">Update</div>
        </details>
    </div> 
</template>

<script>
export default {
    name: 'Card',
    props: ['card'],
    data() {
        return{
            cardstatus : this.card.status
        }
        
    }
}
</script>

<style scoped>
    .card{
        width: 90%;
        margin: 10px auto 0 auto;
        padding: 10px;
        background-color: grey;
        border-radius: 10px;
    }
</style>
