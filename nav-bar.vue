<template>
    <nav class="nav">
      
      <ul class="menu">
        <li><img src="../assets/img/logo.jpeg" height="40" width="150"></li>
        <li id=""><a href="">Home</a></li>
        <li><a href="">Book a ride</a> </li>
        <li><a href="">Transfers</a></li>
        <li><a href="">Request</a></li>
        <li id="tours"><a href="">Tours</a></li>
        <li id="partner"><a href="">Partner</a></li>
        <li>
            <select name="currency" id="currency">
                <option v-for="curr in currency" :value="curr.name" :key="curr.id">{{ curr.name }}</option>
                
            </select>
        </li>
        <li><select name="language" id="language">
            <option v-for="lang in languages" :value="lang.name" :key="lang.id">{{ lang.name }}</option>
        </select></li>
        <li><a href="">Log In</a></li>
        <li id="reg"><a href="">Register</a></li>

      </ul>
     
    </nav>
  </template>
  
  <script>
    export default {
        name: 'AppNavBar',

        data() {
            return {
                currency: [
                    { id: 1, name: 'EUR'},
                    { id: 2, name: 'USD'},
                    { id: 3, name: 'RUB'},
                    { id: 4, name: 'NOK'},
                    { id: 5, name: 'DK'}
                ],
                languages: [
                    { id: 1, name: 'English' },
                    { id: 2, name: 'Russian' },
                    { id: 3, name: 'Chinese' },
                    { id: 4, name: 'French' },
                    { id: 5, name: 'German' }
                ]
            }
        }
    }

</script>
  
  <style scoped>

  

    .menu {
      list-style: none;
      padding: 0;
      margin: 0;
      display: flex;
    }
  
    .menu a {
       text-decoration: none;
       color: white;
       display: inline;
       white-space: nowrap;
       margin-right: 50px; /* Add margin for spacing between items */
    }

    
    .nav {
        
        width: 100%;
        color: white;
        background-color: rgb(59, 28, 144);
        
    }

    #tours {
        margin-right: 200px !important;
        border: solid 2px teal;
        border-radius: 5px;
        padding: 0 2px 0 2px;
    }

    #reg {
        border: solid 2px white;
        border-radius: 5px;
    }

    #partner {
        color: teal;
    }

    
  </style>
  