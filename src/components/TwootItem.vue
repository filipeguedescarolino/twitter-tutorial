<template>
    <div class="twoot-item" @click="favouriteTwoot(twoot.id)">
        <div class="user-profile__twoot" >
            <div class="twoot-item__user">
                @{{username}}
            </div>
            <div class="twoot-item__content">
                {{twoot.content}}
            </div>
        </div>
    </div> 
</template>

<script>

export default {
name: "TwootItem",
props: {
    username: {
        type: String,
        required: true
    },
    twoot: {
        type: Object,
        required: true
    }
},
methods: {
    favouriteTwoot(id) {
        this.$emit('favourite', id)
    }
}
};
</script>

<style>

.twoot-item {
    display: flex;
    flex-direction: row;

}

.user-profile__twoot {
    display: flex;
    cursor: pointer;
    padding: 10px;
    border-radius: 3px;
    font-size: 25px;

}

</style>