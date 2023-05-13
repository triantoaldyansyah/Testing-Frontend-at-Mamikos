<template>
    <div id="app">
        <!-- Search Field -->
        <input
            type="text"
            placeholder="Search"
            class="search-input"
            v-model="searchValue"
        />
        <!-- Data List -->
        <div class="users-container" v-if="usersList.length">
            <div v-for="(user, index) in usersList" 
            :key="index">
                <strong>{{ index + 1 }}.</strong>
                {{ user.name }}
            </div>
        </div>
        <!-- Error Message when data NULL -->
        <div v-else>Name of user that you input is wrong: {{ searchValue }}</div>
    </div>
</template>

<script>
export default {
    name: 'searchFilter',
    components: {},
    // Dummy Data Used
    data: () => ({
      searchValue: '',
      users: [
        { 
            name: 'Anto', 
            age: 24, 
        },
        {   name: 'Aldyansyah',
            age: 27,
        },
        {   name: 'Jurdan',
            age: 25,
        },
        {   name: 'Bryan',
            age: 28,
        },
        {   name: 'Dwiky',
            age: 29,
        },
        {   name: 'Umi', 
            age: 32,
        },
        {   name: 'Salmah',
            age: 22,
        },
        {   name: 'Tri', 
            age: 22,
        },
        {   name: 'Yummy', 
            age: 20,
        },
        {   name: 'Alex', 
            age: 22,
        }
      ],
  }),
  // For display data list
    computed: {
        usersList() {
            if (this.searchValue.trim().length > 0) {
                return this.users.filter((user) =>
                    user.name
                    // For case-insensitive
                    .toLowerCase()
                    .includes(this.searchValue.trim().toLowerCase())
                );
            }
            return this.users;
        },
    },
};
</script>

<style>
    #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: left;
    color: #2c3e50;
    margin-top: 60px;
    }
    .search-input {
        width: 200px;
        height: 30px;
        border-radius: 2px;
    }

    .users-container {
        margin-top: 15px;
    }
</style>  