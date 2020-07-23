<template>
 
        
        <div class="div">
            
            <div class="inp">
                <input type="text" v-model="newtodo" placeholder="Type in something">
                <button  @click="addItem(newtodo)">Add Item</button>
                <button @click="clearAll(newtodo)">Clear All</button>
            </div>
                
                <div class="submit" >

                    <h1
            v-for="(post,k) in posts" v-bind:title="post.data" v-bind:key="k" 
            v-bind:style = '{"text-decoration" : (post.isCompleted? "line-through" : "none" )}' 
            >
            <input type="checkbox" @click="post.isCompleted = !post.isCompleted"> {{ post.data }}
            
            <button id="removeBtn" @click="removeItem(k)">x</button>
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
       
    },

},
mounted(){
    if(localStorage.getItem('posts')) this.posts = JSON.parse(localStorage.getItem('posts'));
},
watch:{
    posts: {
        handler(){
            localStorage.setItem('posts', JSON.stringify(this.posts));
        },
        deep: true,
    }
}
        }

</script>


<style lang="sass" scoped>
    
h1
    
    margin: 2px
    background-color: #f2f2f2
    border-bottom: 1px #ccc dotted
      
#removeBtn
    float: right   
    background-color: #ff5050
    border-radius: 15px  
    padding: 2px 6px
    border-width: 1px
    cursor: pointer



</style>