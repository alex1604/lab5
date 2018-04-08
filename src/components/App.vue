<template>
  <div id="app">
    <div class="banner">
      <img
        src="../../img/tortilla.png"
        width="300"
        alt="vue"
        class="logo"
      />
      <h1>Welcome to iFood</h1>
    </div>
    <div class="bottom">
      <h2>Get started by adding your first recipee!</h2>

      <show-recipees v-for="currentRecipee in recipees" v-bind:key="currentRecipee"
      v-bind:name="currentRecipee.name"
      v-on:my-event="shoppingList"
      v-on:event-hide="hideShoppingList"
      v-bind:description="currentRecipee.description" v-bind:preparationTime="currentRecipee.preparationTime"
      v-bind:showShoppingList="showOrNot" v-bind:ingredientList="myIngredients"/>
    </div>
  </div>

</template>

<script src="../../graf/fontawesome-all.js"></script>
<script>
import ShowRecipees from "./ShowAllRecipees.vue"
export default {
  name: "app",
  components: {
    "show-recipees": ShowRecipees
  },
  data: function() {
    return {
      recipees: [
        {
          name: "Spanish Tortilla",
          ingredients: [
            {
              name: "potato",
              quantity: "1kg"
            },
            {
              name: "egg",
              quantity: "8"
            },
            {
              name: "olive oil",
              quantity: "3dl"
            },
            {
              name: "salt",
              quantity: "5g"
            }
          ],
          description:
            "Wash and peel all the potatos before slicing them. The slices should be around 5mm. After this, add a spoon of olive oil and steer. Prepare the frier/pan and when it's ready start frying the potato slices. In the mean time you can start opening the eggs and blend them with a fork or any manual blending tool. Once all the slices are fried, throw the egg mix into the big bowl where you've previously thrown the potato slices. All the slices should be covered by the egg mix. If so, add the salt and throw in the mix into a very hot pan filled with around 5mm/1cm of olive oil. Turn down the temperature to 4/10 and heck the tortilla every 3-4 mins. When the down side is turning gold, turn the torilla upside down and remove when done.",
          preparationTime: "1.5"
        },
        {
          name: "French Omelette",
          ingredients: [
            {
              name: "egg",
              quantity: "3"
            },
            {
              name: "olive oil",
              quantity: "1 teaspoon"
            },
            {
              name: "salt",
              quantity: "1 pince"
            }
          ],
          description:
            "Crack the eggs and blend them with a fork or any manual blending tool. Add the oil to the pan and throw the egg mix when the oil is warm enough. Turn down the temperature to 4/10. When the down side is turning gold, fold it in by its half and leave on the pan for an extra minute.",
          preparationTime: "0.25"
        },
        {
          name: "Swedish 'kladdkaka'",
          ingredients: [
            {
              name: "butter",
              quantity: "100 g"
            },
            {
              name: "egg",
              quantity: "2"
            },
            {
              name:"plain flour",
              quantity:"150g"
            },
            {
              name:"cocoa powder",
              quantity:"4 teaspoon"
            },
            {
              name:"vanilla sugar",
              quantity:"1 tbsp"
            },
            {
              name: "sugar",
              quantity: "200 g"
            },
            {
              name: "salt",
              quantity: "1 pince"
            }
          ],
          description:
            "Melt the butter and leave to cool slightly. Whisk the egg and sugar together until the mixture is light, fluffy and pale. Weigh all the dry ingredients and sift them into the egg and sugar mixture. Fold in until everything is incorporated. Fold in the melted butter until you are left with a smooth chocolate mixture. Pour into a lined cake tin. This recipe fits a normal tin. The cake will not rise, but it will puff up slightly during baking. Bake at 180°C for around 20 minutes. The exact time can vary, so keep an eye on the cake. A perfect kladdkaka is very soft in the middle, but not runny once it has cooled – but almost runny. If you press down gently on the cake whilst its baking, the crust should need a bit of pressure to crack. When this happens, the cake is done. Leave to cool in the tin for at least an hour.",
          preparationTime: "0.35"
        },
        {
          name: "Slovak gnocchi with bryndza-cheese",
          ingredients: [
            {
              name: "potato",
              quantity: "1 kg"
            },
            {
              name: "flour",
              quantity: "400 g"
            },
            {
              name:"bryndza - cheese",
              quantity:"300 g"
            },
            {
              name:"smoked bacon",
              quantity: "100 g"
            },
            {
              name: "salt",
              quantity: "1 pince"
            },
          ],
          description:
            "Peel potatos, wash and shred them, add salt. Add flour to achive right consistency. Moisten the chopping board, put the part of the dough on it, use a knife to drop a little bit of the dough into the boiling salty water. When gnocchi (in slovak called halušky) are done they will float to the top. Pick them out, add bryndza-cheese and put fried bacon on top.",
          preparationTime: "0.30"
        },
      ],
      thisingredient: Number,
      showOrNot: false,
      myIngredients: '',
    };
  },
  methods: {
    shoppingList: function(event){
      let currentname = event.target.name;
      console.log('current name = ' + currentname)
      for (let index in this.recipees) {
        if (this.recipees[index].name == currentname){
          let ingredients = this.recipees[index].ingredients
          for(let ingredient in ingredients){

            this.myIngredients += '- ' + ingredients[ingredient].name + ' (' + ingredients[ingredient].quantity + ')'
          }
          this.showOrNot = true
        }
      }
    },
    hideShoppingList: function(event){
      this.showOrNot = false
      this.myIngredients = ''
    },

  },
}

/************************************
  RECIPEE OBJEKT:
  {
    name: 'spanish tortilla',
    ingredienser: [
      {
        'name': 'potato'
        'quantity' : '1kg'
      },
      {
        'name': 'egg'
        'quantity' : '8'
      },
      {
        'name': 'olive oil'
        'quantity' : '3dl'
      },
      {
        'name': 'salt'
        'quantity' : '5g'
      }
    ],
    description: '',
    preparationTime: ''
  }
  */
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>
code {
  font-family: Menlo, Monaco, Lucida Console, Liberation Mono, DejaVu Sans Mono,
    Bitstream Vera Sans Mono, Courier New, monospace, serif;
  font-size: 0.9em;
  white-space: pre-wrap;
  color: #2c3e50;
}

code::before,
code::after {
  content: "`";
}
</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
#app {
  text-align: center;
}

#app h1 {
  color: #2c3e50;
  font-weight: 300;
  margin: 0;
}

.banner {
  height: 200px;
  background-color: #f6f6f6;
  padding: 50px 10px;
}

.bottom {
  padding: 80px 10px;
  font-size: 24px;
  font-weight: 300;
  background-color: #F5E1DA ;
}

.fade {
  font-size: 14px;
}

.logo {
  animation: spin 6s 1s infinite linear;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
