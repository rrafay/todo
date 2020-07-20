<template>
 
    
            <!-- <div >
                
            <button class="btn" v-for="post in posts" v-bind:title="post.data" v-bind:key="post.id" 
            v-bind:style = '{"text-decoration" : (post.isCompleted? "line-through" : "none" )}' 
            @click="post.isCompleted = !post.isCompleted">
                
                {{ post.data }}
                
               
            </button>
             </div> -->
            
       

        
        <div class="div">
            <h1
            v-for="post in posts" v-bind:title="post.data" v-bind:key="post.id" 
            v-bind:style = '{"text-decoration" : (post.isCompleted? "line-through" : "none" )}' 
            >
            <input type="checkbox" @click="post.isCompleted = !post.isCompleted"> {{ post.data }}
            </h1>

        </div>
    

  
</template>

<script>
export default {
    data : function(){
        return{
            name : 'Rafay',
            count : 0,
            posts:[
                {id: 1 , data: 'Milk', isCompleted: false},
                {id: 2 , data: 'Eggs', isCompleted : true},
                {id: 3 , data: 'Toast', isCompleted: false},
                {id: 4, data: 'Coffee', isCompleted: false}
            ]
             
       
    }
    
},
methods : {
    completedTask: function (){
     this.posts.isCompleted = !this.posts.isCompleted; 
     //return console.log("event happening");
     //return console.log(this.posts.isCompleted = !this.posts.isCompleted)
     
     }
        }
        }

</script>


<style lang="sass" scoped>
    
.active
    text-decoration: line-through

.not-active
    text-decoration: none
    color: blue   

.btn
      
    
</style>