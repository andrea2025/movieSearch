<template>
    <div>
        <p ref="dom-element">{{text1}}</p>
       <div> <input type="search" placeholder="search movie" v-model="search" >
       <button @click="filerImage">search</button>
       </div>
       <p v-for="(item,index) in imageTotal" :key="index">{{imge.Name}} </p>
        <div class="imageWrapper">
            <div v-for='(imge,index) in imageGroup' :key="index">
                
                    <img :src="imge.Url" class="imageItem">
                    <p>{{imge.Name}}</p>
                        <p>{{imge.Type}}</p>
                    
                  
                  <button @click="del(index)">delete</button>
                
             </div>
        </div>
    </div>
    
</template>
<script>
export default {
    name:'movieSearch',
     updated() {
    // Fired every second, should always be true
    return(+this.$refs['dom-element'].textContent === this.counter)
  },

  created() {
    setInterval(() => {
      this.counter += 5
    }, 5000)
  },
    data(){
        return{

            imageGroup:[
  {
    Name: "John Frusciante",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/152457.jpg",
  },
  {
    Name: "Reservoir Dogs",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Foo Fighters",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151457.jpg"
  },
  {
    Name: "Pearl Jam",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/150357.jpg"
  },
  {
    Name: "Sublime",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151377.jpg"
  },
  {
    Name: "Inglourious Basterds",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151227.jpg"
  },
  {
    Name: "Incubus",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Audioslave",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Jackie Brown",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151367.jpg"
  },
  {
    Name: "Nirvana",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151358.jpg"
  },
  {
    Name: "The Big Lebowski",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Goodfellas",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151997.jpg"
  },
  {
    Name: "Guns N' Roses",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Death Proof",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "The Offspring",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Django Unchained",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Rage Against The Machine",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Snatch",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Trainspotting",
    Type: "movie",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
  },
  {
    Name: "Weezer",
    Type: "music",
    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/152357.jpg"
  }
],
            search:'',
            searched:false,
            imageTotal:[],
            counter:0,
            text1:"loading...."
        }
        
    },
    methods: {
            del(index) {
             this.imageGroup.splice(index, 1)
         },
          filerImage(){
            this.imageTotal= this.imageGroup.filter(imge => {return imge.Name === this.search});
            this.searched = true;

        }
    },

    computed:{
        imageGroup(){
           if (this.searched) {
          return this.imageTotal;
        }else return this.imageGroup
    }

    }
    
</script>

<style scoped>
*{
    margin-top: 2em;
}
.imageWrapper{
    display: grid;
    grid-template-columns: auto auto auto;
}
.imageItem{
    width: 70%;
    height: 200px;
}
button{
    background: chocolate;
    color: white;
    margin:2em;
}
</style>