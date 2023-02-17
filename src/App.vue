<template>
  <section>
    <header><h1>My Friends</h1></header>
    <ul>
      <friend-contact
        v-for="friend in friends"
        :key="friend.id"
        :id="friend.id"
        :name="friend.name"
        :phone-number="friend.phone"
        :email-address="friend.email"
        :is-favorite="friend.isFavorite"
        @toggle-favorite="toggleFavoriteStatus"
      ></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  data () {
    return {
      friends: [
        {
          id: 'nikki',
          name: 'Nikki Erwin',
          phone: '123 456 7890',
          email: 'lovelylady@gmail.com',
          isFavorite: true
        },
        {
          id: 'kevin',
          name: 'Kevin Kensley',
          phone: '987 654 3210',
          email: 'snipesac@gmail.com',
          isFavorite: false
        }
      ]
    }
  },
  methods: {
    toggleFavoriteStatus (friendId) {
      const identifiedFriend = this.friends.find(
        friend => friend.id === friendId
      )
      identifiedFriend.isFavorite = !identifiedFriend.isFavorite
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');
* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #15095b;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #201e1e;
  margin: 0 0 1rem 0;
}

#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #15095b;
  border-radius: 8px;
  background-color: #15095b;
  color: white;
  padding: 0.3rem 1rem;
  margin: 0 5px;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#app button:hover,
#app button:active {
  background-color: #201e1e;
  border-color: #201e1e;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>
