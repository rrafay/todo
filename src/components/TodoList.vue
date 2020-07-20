<template>
 
    
            <!-- <div >
                
            <button class="btn" v-for="post in posts" v-bind:title="post.data" v-bind:key="post.id" 
            v-bind:style = '{"text-decoration" : (post.isCompleted? "line-through" : "none" )}' 
            @click="post.isCompleted = !post.isCompleted">
                
                {{ post.data }}
                
               
            </button>
             </div> -->
            
       

        
        <div class="div">
            
            <div class="inp">
                <input type="text" v-model="posts.data" placeholder="Type in something">
                <button  @click="addItem(posts.data)">Add Item</button>
                <button @click="clearAll(posts.id)">Clear All</button>
            </div>
                
                <div class="submit" >

                    <h1
            v-for="(post,k) in posts" v-bind:title="post.data" v-bind:key="k" 
            v-bind:style = '{"text-decoration" : (post.isCompleted? "line-through" : "none" )}' 
            >
            <input type="checkbox" @click="post.isCompleted = !post.isCompleted"> {{ post.data }}
            
            <button class="removeBtn" @click="removeItem(k)">x</button>
            </h1>
                    
                </div>
  

        </div>
    

  
</template>

<script>
export default {
    name:'TodoList',
    data : function(){
        return{
            name : 'Rafay',
            count : 0,
            posts:[
                
                
            ]
             
       
    }
    
},
methods: {
    addItem(index) {
      this.posts.push({data: index, isCompleted:false});
      
    },
    clearAll(index){
        this.posts.splice({data: index});
    },
    removeItem(index){
        this.posts.splice(index, 1);
    }
}
        }

</script>


<style lang="sass" scoped>
    
h1
    
    margin: 2px
    background-color: #f2f2f2
    border-bottom: 1px #ccc dotted
      
.removeBtn
    float: right   
    background-color: #ff5050
    border-radius: 15px  
    padding: 2px 6px
    border-width: 1px
    cursor: pointer



</style>