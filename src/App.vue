<template>
 <div>
   <h1>Hello vue component</h1>
   <my-header></my-header>
   <my-counter></my-counter>
    <form @submit.prevent="handleSubmit">
     <fieldset style="width: 40%;">
    <legend>Form</legend>
       <div>
         <label for="name">Name</label>
         <input type="name" placeholder="Name"  v-model="name" />
       </div>
       <div>
         <label for="comment">Comment</label>
         <textarea  placeholder="Comment" v-model="comment" ></textarea>
       </div>
        <div>
          <input type="checkbox" id="coding" v-model="hobbies1" />
          <label for="coding">Games</label>
        </div>
        <div>
          <input type="checkbox" id="music" v-model="hobbies" />
          <label for="music">Music</label>
        </div>
        <select v-model="rating">
         <option disabled value="">Choose your Rating</option>
          <option>1</option>
          <option>2</option>
          <option>3</option>
          <option>4</option>
          <option>5</option>
        </select>
        <div>
          <input type="radio" id="male" value="Male" v-model="gender" />
          <label for="male">Male</label>
        </div>
        <div>
          <input type="radio" id="female" value="Female" v-model="gender" />
          <label for="female">Female</label>
        </div>
       </fieldset>
        <button type="submit">Submit</button>
     </form>
     <p>My name is: {{name}}</p>
     <p style="white-space:pre-line">
         My comment is: {{comment}}
      </p>
      <p>You've rated: {{ rating }}</p>
      <p>Gender: {{ gender }}</p>
 </div>
</template>

<script>
import Header from './components/Header'
import Counter from './components/Counter'
  export default {
     components:{
         'my-header':Header,
         'my-counter':Counter,
     },
     data:function(){
        return{
          name:'',
           comment:'',
            hobbies: [],
            rating: "",
            gender:""
        }
      },
      methods:{
      handleSubmit:function(){
          console.log('Name'.this.name);
          console.log('Comment'.this.comment);
          console.log('Rating'.this.rating);
          console.log('Gender'.this.gender);
      }
  }
  }
</script>

<style>
  *{
      box-sizing:border-box;
      margin:0;
  }
</style>