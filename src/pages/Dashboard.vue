<template>
  <v-flex xs12 row>
  	<v-layout row wrap>
	  	<v-flex xs12 sm6 md3 pa-2>
	      <v-card class="elevation-2">
	        <v-card-title>
	          <v-flex xs6>
	          	<v-icon class="green--text" size="72">how_to_reg</v-icon>
	          </v-flex>
	    	  <v-flex xs6 class="text-xs-right">
		        <h3 class="display-2 grey--text">72K</h3>
		        <h6 class="caption grey--text text--lighten-1">Customers</h6>
	    	  </v-flex>
	        </v-card-title>
	        <v-divider></v-divider>
	        <v-card-actions>
	          <div class="body-1 grey--text text--lighten-1">THIS YEAR</div>
	        </v-card-actions>
	      </v-card>
	    </v-flex>
	    <v-flex xs12 sm6 md3 pa-2>
	      <v-card class="elevation-2">
	        <v-card-title>
	          <v-flex xs6>
	          	<v-icon class="amber--text" size="72">shopping_cart</v-icon>
	          </v-flex>
	    	  <v-flex xs6 class="text-xs-right">
		        <h3 class="display-2 grey--text">31K</h3>
		        <h6 class="caption grey--text text--lighten-1">SALES</h6>
	    	  </v-flex>
	        </v-card-title>
	        <v-divider></v-divider>
	        <v-card-actions>
	          <div class="body-1 grey--text text--lighten-1">THIS MONTH</div>
	        </v-card-actions>
	      </v-card>
	    </v-flex>
	    <v-flex xs12 sm6 md3 pa-2>
	      <v-card class="elevation-2">
	        <v-card-title>
	          <v-flex xs6>
	          	<v-icon class="deep-orange--text" size="72">attach_money</v-icon>
	          </v-flex>
	    	  <v-flex xs6 class="text-xs-right">
		        <h3 class="display-2 grey--text">95K</h3>
		        <h6 class="caption grey--text text--lighten-1">Revenue</h6>
	    	  </v-flex>
	        </v-card-title>
	        <v-divider></v-divider>
	        <v-card-actions>
	          <div class="body-1 grey--text text--lighten-1">THIS MONTH</div>
	        </v-card-actions>
	      </v-card>
	    </v-flex>
	    <v-flex xs12 sm6 md3 pa-2>
	      <v-card class="elevation-2">
	        <v-card-title>
	          <v-flex xs6>
	          	<v-icon class="pink--text" size="72">work_outline</v-icon>
	          </v-flex>
	    	  <v-flex xs6 class="text-xs-right">
		        <h3 class="display-2 grey--text">4K</h3>
		        <h6 class="caption grey--text text--lighten-1">Bookings</h6>
	    	  </v-flex>
	        </v-card-title>
	        <v-divider></v-divider>
	        <v-card-actions>
	          <div class="body-1 grey--text text--lighten-1">THIS WEEK</div>
	        </v-card-actions>
	      </v-card>
	    </v-flex>
    </v-layout>

    <v-layout pt-3>
	    <v-flex xs12>
	    	<div class="text-xs-center">
			    <v-chip color="indigo" text-color="white">
			      <v-avatar>
			        <v-icon>account_circle</v-icon>
			      </v-avatar>
			      Ranee
			    </v-chip>

			    <v-chip color="orange" text-color="white">
			      Premium
			      <v-icon right>star</v-icon>
			    </v-chip>

			    <v-chip color="primary" text-color="white">
			      1 Year
			      <v-icon right>cake</v-icon>
			    </v-chip>

			    <v-chip color="green" text-color="white">
			      <v-avatar class="green darken-4">1</v-avatar>
			      Years
			    </v-chip>

			    <v-chip close color="teal" text-color="white">
			      <v-avatar>
			        <v-icon>check_circle</v-icon>
			      </v-avatar>
			      Confirmed
			    </v-chip>
			  </div>
	    </v-flex>
    </v-layout>

	<v-layout py-3>
	   		<v-flex xs12 sm10 offset-sm1>
	   			<v-card>
		   			<v-card-title>
				      <div class="title">Nutrition Table</div>
				      <v-spacer></v-spacer>
				      <v-text-field
				        v-model="search"
				        append-icon="search"
				        label="Search"
				        single-line
				        hide-details
				      ></v-text-field>
				    </v-card-title>
		   			<v-data-table
					    :headers="headers"
					    :loading="true"
					    :items="desserts"
					    :search="search"
					    v-model="selected"
					    item-key="name"
					    select-all
					  >
					  	<v-progress-linear slot="progress" color="blue" indeterminate></v-progress-linear>
					    <template slot="headerCell" slot-scope="props">
					      <v-tooltip bottom>
					        <span slot="activator">
					          {{ props.header.text }}
					        </span>
					        <span>
					          {{ props.header.text }}
					        </span>
					      </v-tooltip>
					    </template>
					    <template slot="items" slot-scope="props">
					      <td>
					        <v-checkbox
					          v-model="props.selected"
					          primary
					          hide-details
					        ></v-checkbox>
					      </td>
					      <td>{{ props.item.name }}</td>
					      <td class="text-xs-right">{{ props.item.calories }}</td>
					      <td class="text-xs-right">{{ props.item.fat }}</td>
					      <td class="text-xs-right">{{ props.item.carbs }}</td>
					      <td class="text-xs-right">{{ props.item.protein }}</td>
					      <td class="text-xs-right">{{ props.item.iron }}</td>
					    </template>
					  </v-data-table>
				</v-card>
	   		</v-flex>
	   </v-layout>
    
    <v-layout row wrap>
	    <v-flex sm12 md4 px-2 py-4>
	      <v-card>
	        <v-toolbar color="pink" dark>
	          <v-toolbar-side-icon></v-toolbar-side-icon>
	          <v-toolbar-title>Inbox</v-toolbar-title>
	          <v-spacer></v-spacer>
	          <v-btn icon>
	            <v-icon>search</v-icon>
	          </v-btn>
	          <v-btn icon>
	            <v-icon>check_circle</v-icon>
	          </v-btn>
	        </v-toolbar>
	        <v-list two-line>
	          <template v-for="(item, index) in items">
	            <v-list-tile :key="index" avatar ripple @click="">
	              <v-list-tile-content>
	                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
	                <v-list-tile-sub-title class="text--primary">{{ item.headline }}</v-list-tile-sub-title>
	                <v-list-tile-sub-title>{{ item.subtitle }}</v-list-tile-sub-title>
	              </v-list-tile-content>
	              <v-list-tile-action>
	                <v-list-tile-action-text>{{ item.action }}</v-list-tile-action-text>
	                <v-icon color="grey lighten-1">star_border</v-icon>
	              </v-list-tile-action>
	            </v-list-tile>
	            <v-divider v-if="index + 1 < items.length" :key="`divider-${index}`"></v-divider>
	          </template>
	        </v-list>
	      </v-card>
	    </v-flex>
	    <v-flex sm12 md4 px-2 py-4>
	      <v-card>
	        <v-toolbar color="light-blue" dark>
	          <v-toolbar-side-icon></v-toolbar-side-icon>
	          <v-toolbar-title>My files</v-toolbar-title>
	          <v-spacer></v-spacer>
	          <v-btn dark icon>
	            <v-icon>search</v-icon>
	          </v-btn>
	          <v-btn dark icon>
	            <v-icon>view_module</v-icon>
	          </v-btn>
	        </v-toolbar>
	        <v-list two-line subheader>
	          <v-subheader inset>Folders</v-subheader>
	          <v-list-tile v-for="item in items2" :key="item.title" avatar @click="">
	            <v-list-tile-avatar>
	              <v-icon :class="[item.iconClass]">{{ item.icon }}</v-icon>
	            </v-list-tile-avatar>
	            <v-list-tile-content>
	              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
	              <v-list-tile-sub-title>{{ item.subtitle }}</v-list-tile-sub-title>
	            </v-list-tile-content>
	            <v-list-tile-action>
	              <v-btn icon>
	                <v-icon color="grey lighten-1">info</v-icon>
	              </v-btn>
	            </v-list-tile-action>
	          </v-list-tile>
	          <v-divider inset></v-divider>
	          <v-subheader inset>Files</v-subheader>
	          <v-list-tile v-for="item in items3" :key="item.title" @click="">
	            <v-list-tile-avatar>
	              <v-icon :class="[item.iconClass]">{{ item.icon }}</v-icon>
	            </v-list-tile-avatar>
	            <v-list-tile-content>
	              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
	              <v-list-tile-sub-title>{{ item.subtitle }}</v-list-tile-sub-title>
	            </v-list-tile-content>
	            <v-list-tile-action>
	              <v-btn icon>
	                <v-icon color="grey lighten-1">info</v-icon>
	              </v-btn>
	            </v-list-tile-action>
	          </v-list-tile>
	        </v-list>
	      </v-card>
	    </v-flex>
	    <v-flex sm12 md4 px-2 py-4>
	      <v-card>
	        <v-card-title class="cyan darken-1">
	          <span class="headline white--text">Sarah</span>
	          <v-spacer></v-spacer>
	          <v-btn dark icon>
	            <v-icon>chevron_left</v-icon>
	          </v-btn>
	          <v-btn dark icon>
	            <v-icon>edit</v-icon>
	          </v-btn>
	          <v-btn dark icon>
	            <v-icon>more_vert</v-icon>
	          </v-btn>
	        </v-card-title>
	        <v-list two-line>
	          <v-list-tile @click="">
	            <v-list-tile-action>
	              <v-icon>phone</v-icon>
	            </v-list-tile-action>
	            <v-list-tile-content>
	              <v-list-tile-title>(650) 555-1234</v-list-tile-title>
	            </v-list-tile-content>
	            <v-list-tile-action>
	              <v-icon>chat</v-icon>
	            </v-list-tile-action>
	          </v-list-tile>
	          <v-divider inset></v-divider>
	          <v-list-tile @click="">
	            <v-list-tile-action>
	              <v-icon>phone</v-icon>
	            </v-list-tile-action>
	            <v-list-tile-content>
	              <v-list-tile-title>(323) 555-6789</v-list-tile-title>
	            </v-list-tile-content>
	            <v-list-tile-action>
	              <v-icon>chat</v-icon>
	            </v-list-tile-action>
	          </v-list-tile>
	          <v-divider inset></v-divider>
	          <v-list-tile @click="">
	            <v-list-tile-action>
	              <v-icon>mail</v-icon>
	            </v-list-tile-action>
	            <v-list-tile-content>
	              <v-list-tile-title>mcbeal@example.com</v-list-tile-title>
	            </v-list-tile-content>
	          </v-list-tile>
	          <v-divider inset></v-divider>
	          <v-list-tile @click="">
	            <v-list-tile-action>
	              <v-icon>location_on</v-icon>
	            </v-list-tile-action>
	            <v-list-tile-content>
	              <v-list-tile-title>Orlando, FL 79938</v-list-tile-title>
	            </v-list-tile-content>
	          </v-list-tile>
	        </v-list>
	        <v-card-media src="https://picsum.photos/700?image=996" height="200px">
	        </v-card-media>
	      </v-card>
	    </v-flex>
	  </v-layout>
	  <v-layout row wrap>
	    <v-flex sm12 md8 px-2 py-3>
	    	<v-stepper v-model="e6" vertical>
			    <v-stepper-step :complete="e6 > 1" step="1">
			      Select an app
			      <small>Summarize if needed</small>
			    </v-stepper-step>
			    <v-stepper-content step="1">
			      <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
			      <v-btn color="primary" @click.native="e6 = 2">Continue</v-btn>
			      <v-btn flat>Cancel</v-btn>
			    </v-stepper-content>
			    <v-stepper-step :complete="e6 > 2" step="2">Configure analytics for this app</v-stepper-step>
			    <v-stepper-content step="2">
			      <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
			      <v-btn color="primary" @click.native="e6 = 3">Continue</v-btn>
			      <v-btn flat>Cancel</v-btn>
			    </v-stepper-content>
			    <v-stepper-step :complete="e6 > 3" step="3">Select an ad format and name ad unit</v-stepper-step>
			    <v-stepper-content step="3">
			      <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
			      <v-btn color="primary" @click.native="e6 = 4">Continue</v-btn>
			      <v-btn flat>Cancel</v-btn>
			    </v-stepper-content>
			    <v-stepper-step step="4">View setup instructions</v-stepper-step>
			    <v-stepper-content step="4">
			      <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
			      <v-btn color="primary" @click.native="e6 = 1">Continue</v-btn>
			      <v-btn flat>Cancel</v-btn>
			    </v-stepper-content>
			  </v-stepper>
	    </v-flex>
	    <v-flex sm12 md4 px-2 py-3>
	      <v-card>
	        <v-toolbar flat>
	          <v-btn icon>
	            <v-icon>arrow_back</v-icon>
	          </v-btn>
	          <v-toolbar-title>Albums</v-toolbar-title>
	          <v-spacer></v-spacer>
	          <v-btn icon>
	            <v-icon>search</v-icon>
	          </v-btn>
	        </v-toolbar>
	        <v-subheader>May</v-subheader>
	        <v-container fluid grid-list-sm>
	          <v-layout row wrap>
	            <v-flex v-for="i in 6" :key="i" xs4>
	              <img :src="`https://randomuser.me/api/portraits/men/${i + 20}.jpg`" class="image" alt="lorem" width="100%" height="100%">
	            </v-flex>
	          </v-layout>
	        </v-container>
	        <v-subheader>June</v-subheader>
	        <v-container fluid grid-list-sm>
	          <v-layout row wrap>
	            <v-flex v-for="i in 6" :key="i" xs4>
	              <img :src="`https://randomuser.me/api/portraits/women/${i + 5}.jpg`" class="image" alt="lorem" width="100%" height="100%">
	            </v-flex>
	          </v-layout>
	        </v-container>
	      </v-card>
	    </v-flex>
	   </v-layout>
  </v-flex>
</template>

<script>

  export default {
    name: 'Dashboard',
    data () {
      return {
        items: [
          { action: '15 min', headline: 'Brunch this weekend?', title: 'Ali Connors', subtitle: "I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { action: '2 hr', headline: 'Summer BBQ', title: 'me, Scrott, Jennifer', subtitle: "Wish I could come, but I'm out of town this weekend." },
          { action: '6 hr', headline: 'Oui oui', title: 'Sandra Adams', subtitle: 'Do you have Paris recommendations? Have you ever been?' },
          { action: '12 hr', headline: 'Birthday gift', title: 'Trevor Hansen', subtitle: 'Have any ideas about what we should get Heidi for her birthday?' },
          { action: '18hr', headline: 'Recipe to try', title: 'Britta Holt', subtitle: 'We should eat this: Grate, Squash, Corn, and tomatillo Tacos.' },
          { action: '6 hr', headline: 'Oui oui', title: 'Sandra Adams', subtitle: 'Do you have Paris recommendations? Have you ever been?' },
          { action: '15 min', headline: 'Brunch this weekend?', title: 'Ali Connors', subtitle: "I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" }
        ],
        items2: [
          { icon: 'folder', iconClass: 'grey lighten-1 white--text', title: 'Photos', subtitle: 'Jan 9, 2014' },
          { icon: 'folder', iconClass: 'grey lighten-1 white--text', title: 'Recipes', subtitle: 'Jan 17, 2014' },
          { icon: 'folder', iconClass: 'grey lighten-1 white--text', title: 'Work', subtitle: 'Jan 28, 2014' },
          { icon: 'folder', iconClass: 'grey lighten-1 white--text', title: 'Videos', subtitle: 'Feb 14, 2014' },
        ],
        items3: [
          { icon: 'assignment', iconClass: 'blue white--text', title: 'Vacation itinerary', subtitle: 'Jan 20, 2014' },
          { icon: 'call_to_action', iconClass: 'amber white--text', title: 'Kitchen remodel', subtitle: 'Jan 10, 2014' }
        ],
        e6: 1,
        search: '',
        selected: [],
        headers: [
          {
            text: 'Dessert (100g serving)',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'Calories', value: 'calories' },
          { text: 'Fat (g)', value: 'fat' },
          { text: 'Carbs (g)', value: 'carbs' },
          { text: 'Protein (g)', value: 'protein' },
          { text: 'Iron (%)', value: 'iron' }
        ],
        desserts: [
          {
            value: false,
            name: 'Frozen Yogurt',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
            iron: '1%'
          },
          {
            value: false,
            name: 'Ice cream sandwich',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
            iron: '1%'
          },
          {
            value: false,
            name: 'Eclair',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0,
            iron: '7%'
          },
          {
            value: false,
            name: 'Cupcake',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3,
            iron: '8%'
          },
          {
            value: false,
            name: 'Gingerbread',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9,
            iron: '16%'
          },
          {
            value: false,
            name: 'Jelly bean',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0,
            iron: '0%'
          },
          {
            value: false,
            name: 'Lollipop',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0,
            iron: '2%'
          },
          {
            value: false,
            name: 'Honeycomb',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5,
            iron: '45%'
          },
          {
            value: false,
            name: 'Donut',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9,
            iron: '22%'
          },
          {
            value: false,
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            iron: '6%'
          }
        ]
      }
    },
    created: function(){
      this.$root.breadcrumbs = []
    }
  }
</script>
