<template>
    <div class="user-profile">
        <div class="user-profile__user-panel">
            <h1 class="user-profile__username">@{{user.userName}}</h1>
            <div class="user-profile__follower-count"> 
                <strong> Followers: </strong> {{followers}}
            </div>
        </div>
    </div>
</template>


<script>
export default {
    data() {
    return {
      followers: 0,
      user: {
        id: 1,
        userName: 'FilipeCarolino',
        firstName: 'Filipe',
        lastName: 'Guedes',
        email: 'filipe.guedes@gmail.com',
        isAdmin: true

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
    }
  
  },
  mounted() {
    this.followUser();
  }
  
}

</script>


<style scoped>

</style>