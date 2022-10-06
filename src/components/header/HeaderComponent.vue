<template>
<header>
    <!-- <script src="https://kit.fontawesome.com/710259c6f3.js" crossorigin="anonymous"></script> -->
    <div class="img-container">
        <img src="@/assets/img/dark-logo.png" alt="max_coach_logo">
    </div>
    <div class="lists-container">
        <div class="list" v-for="list in dropdowns" :key="list.title" @click="setActiveList(list)" >
            {{list.title}} <i class="fa-solid fa-caret-down"></i>
            <div v-if="list === activeIndex">
                <ul>
                    <li v-for="link in list.links" :key="link.name">
                        <a :href="link.link">{{link.name}}</a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    <div>
        language
        search
    </div>
</header>
</template>

<script>

import dropdowns from '@/data/headerDropdowns.json';

export default {
    name: 'HeaderComponent',
    data(){
        return {
            dropdowns,
            activeIndex: 0
        }
    },
    mounted(){
        console.log('dropdown lists in header: ',dropdowns);
    },
    methods:{
        setActiveList(i){
            if(i == this.activeIndex){
                return this.activeIndex = 0;
            }
            this.activeIndex = i;
            return this.activeIndex;
        }


    }
}
</script>

<style lang="scss" scoped>
@import '@/main.scss';
header{
    @include flex-row;
    justify-content: space-between;
    align-items: center;
    padding: 0% 2%;
    font-size: 0.9rem;
    min-height: 7vh;
    max-height: 7vh;
    width: 100%;
    border: solid black 1px;
    .img-container{
        transform: translateX(70%);
        img{
            height: 3vh;
        }
    }
    .lists-container{
        @include flex-row;
        .list{
            @include flex-col;
            position: relative;
            margin: 0px 14px;
            ul{
                position: absolute;
                list-style-type: none;
                padding: 0px 5px;
                background-color: white;
                border: solid black 1px;
                li{
                    margin: 7px 0px;
                    a{
                        color: black;
                    }
                    
                }
            }
        }
        
    }
}


</style>