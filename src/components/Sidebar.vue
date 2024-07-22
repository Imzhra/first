<template>
    <v-card style="background-color:gold;">
      <v-container >
        
        <v-window v-model="step">
            <v-window-item :value="1">
                <v-app-bar  color="yellow">
          <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer" style="color: black;"></v-app-bar-nav-icon>
          <v-toolbar-title style="color: black;">Welcome To Daily Shop</v-toolbar-title>
          <v-spacer></v-spacer>
          
        </v-app-bar>
  
        <v-navigation-drawer v-model="drawer" temporary style="background-color:yellow;">
          <v-list>
            <v-list-item-group>
              <v-list-item v-for="item in items" :key="item.text" :to="item.route" link>
                <v-list-item-action>
                  <v-icon>{{ item.icon }}</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                  <v-list-item-title>{{ item.text }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
        </v-navigation-drawer>
        <div>
            <v-row style="display:flex;padding-bottom: 400px; margin-left:900px; margin-top: 100px;" >
            <v-col cols="40" md="30">
                <v-form @submit.prevent="submitForm" >
                    <h1 style="display: flex; align-items: center;justify-content: center; ">Login</h1>
                    <v-text-field v-model="text" label="Username"></v-text-field>
                    <v-text-field v-model="email" label="Email"></v-text-field>
                    <v-btn type="submit" style="margin-left: 100px;">Submit</v-btn> <br>
                    
                    
                    <h5 style="margin-left: 70px; margin-top: 5px;">  Dont Have An Account?</h5>
                    <v-btn style="margin-left: 100px ; margin-top: 10px;" @click="step++">Sign Up</v-btn>
               </v-form>
            </v-col>
        </v-row>
        </div>

        
            </v-window-item>
            <v-window-item :value="2">
                
                             <v-btn @click="step--">
                                <v-icon style="color: blue;">fas fa-arrow-left</v-icon>
                            </v-btn>
                <div>
                    <v-row style="display:flex; padding-bottom: 200px;" align="center" justify="center" >
                        <v-col cols="40" md="30">
                            <v-form @submit.prevent="submitForm" >
                            <h1 style="display: flex; align-items: center;justify-content: center; ">SignUp</h1>
                            <v-text-field v-model="text" label="Username"></v-text-field>
                            <v-text-field v-model="password" label="Password"></v-text-field>
                            <v-text-field v-model="email" label="Email"></v-text-field>
                            <v-text-field v-model="text" label="Gender"></v-text-field>
                            <div style="text-align: center;">
                                <v-btn type="submit" style="margin-left: auto; margin-right: auto;">Submit</v-btn> <br>
                                <div style="text-align: center;">
                                    <h4 style="display: inline-block; margin-top: 20px;">Remember Me</h4>
                                    <v-checkbox style="display: inline-block; vertical-align: middle; margin-top: 10px;"></v-checkbox>
                                    </div>

                            </div>
                            
                            
                            
                            <h5 style="margin-left: 100px; margin-top: 30px;"> Or Continue With</h5><br>
                            <div class="d-flex justify-space-between align-center mx-10 mb-16">
                                <v-btn>
                                <v-icon color="red">fa-brands fa-google</v-icon>
                            </v-btn>
                            <v-btn >
                                <v-icon color="blue-lighten-3">fa-brands fa-twitter</v-icon>
                            </v-btn>
                            <v-btn>
                                <v-icon color="blue">fa-brands fa-facebook</v-icon>
                            </v-btn>
                            </div>
                            
                            
                            </v-form>
                        </v-col>
                    </v-row>
                </div>
                

            </v-window-item>
        </v-window> 
      </v-container>    
    </v-card>
  </template>
  
  <script>
  export default {
    data: () => ({
      drawer: false,
      step : 1,
      items: [
        { icon: 'fas fa-user', text: 'User', route: '/user' },
        { icon: 'fas fa-store', text: 'Store', route: '/shopping-page' },
        { icon: 'fas fa-question', text: 'About Us', route: '/about-us' },
      ],

    
    }),
    methods: {
    submitForm() {
      // Handle form submission logic here
      console.log('Form submitted with data:', this.formData);
  },
}
  }
</script>

  