<template>
    <div class="user-profile">
        <div class="user-profile__user-panel">
            <h1 class="user-profile__username">@{{user.userName}}</h1>
            <div class="user-profile__admin" v-if="user.isAdmin"> 
                Admin
            </div>
            
            <div class="user-profile__follower-count" > 
                <strong> Followers: </strong> {{followers}}
            </div>
        </div>
        <div class="user-profile__twoots-wrapper">
            <TwootItem  
            v-for="twoot in user.twoot" 
            :key="twoot.id" 
            :username="user.username" 
            :twoot="twoot"
            @favourite="toggleFavourite"
            />
        </div>
    </div>
</template>


<script>

import TwootItem from './TwootItem'
export default {
    name: "userProfile",
    components: {
        TwootItem
    },
    data() {
    return {
      followers: 0,
      user: {
        id: 1,
        userName: 'FilipeCarolino',
        firstName: 'Filipe',
        lastName: 'Guedes',
        email: 'filipe.guedes@gmail.com',
        isAdmin: true,
        twoot: [
            {id: 1, content: "Your website is awesome"},
            {id: 2, content:  "is awesome"},
            {id:3, content: 'Programador'},
            {id: 4, content: 'Que máquina'}
        ]

      }
    }
  },

  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if (oldFollowerCount < newFollowerCount) {
        console.log(`${this.user.userName} has gained a new follower`)
      } 
    }
  },


  computed: {
    fullName() {
      return this.user.firstName +  this.user.lastName
    }
  },
  
  methods: {
    followUser() {
      this.followers++
    },
    toggleFavourite(id) {
        console.log(`Favourited Twoot: ${id}`)
    },
  
  },
  mounted() {
    this.followUser();
  }
  
}

</script>

<style>

.user-profile__admin {
    background: purple;
    color: white;
    border-radius: 5px;
    margin: auto;
    padding: 5px;
}

/* .user-profile-twoot {
    background: red;
    font-size: 20px;
} */

</style>