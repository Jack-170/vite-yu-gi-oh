<script>

export default{
    name:'Appheader',

    props:['message'],

    methods:{
        GetImagePath: function(imgPath){
            return new URL(imgPath, import.meta.url ).href;
        }
    }
}

</script>

<template>


<header>

    <div class="container-fluid">

        <div class="navbar d-flex justify-content-start">
    
           <div class="ms-box-img">
            <img src="../assets/logo.png" alt="">
           </div>
    
           <h2>{{ message }}</h2>
    
        </div>
    
     </div>
    
</header>
 
  
</template>

<style lang="scss" scoped>

@use '../styles/general.scss' as *;



header{
    height: 90px;

    .container-fluid{
        height: 100%;
    
        .navbar{
            height: 70px;
            margin: 10px auto;
    
            .ms-box-img{
                height: 40px;
                width: 100px;
                object-fit: contain;
    
                img{
                    width: 100%;
                    height: 100%;
                }
            }
        }
    }
}





</style>
