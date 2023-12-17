<template>
<div class="container">
    <div class="content">
        <div class="wrapper">
            <div class="nav-bar">
                <text :class="{activePage: page == 'home'}" @click="page = 'home'">Главная</text>
                <text :class="{activePage: page == 'laws'}" @click="page = 'laws'">Законы</text>
            </div>
            <div class="cards">
                <div class="home" v-if="page == 'home'" v-for="i in 100">
                    <HomeCardView :num="i" />
                </div>
                <div class="laws" v-if="page == 'laws'">
                    <LawsLawView />
                </div>
            </div>
        </div>
        <div class ="search-bar">
            <input type="text" v-model="search" placeholder="Поиск..." />
            {{ search }}
        </div>
    </div>
</div>
</template>
<script>
export default{
    data(){
        return{
            page: 'home',
            search: ''
        }
    }
}
</script>
<sytle scoped lang="scss">
.container{
    width: 100vw;
    display: flex;
    flex-direction: row;
}
.content{
    background-color: var(--post-background);
    width: 1440px;
    margin-left: auto;
    margin-right: auto;
    display: flex;
    flex-direction: row;
    .wrapper{
        background-color: var(--content-color);
        width: 65%;
        margin-top: 40px;
        margin-bottom: 40px;
        border-radius: 6px; 
        padding: 8px 16px;
        .nav-bar{
            text-align: left;
            text{
                margin-right: 10px;
                cursor: pointer;
            }
            .activePage{
                color: #72A5AC;
                text-decoration: underline;
            }
        }
        .cards{
            margin-top: 10px;
            display: flex;
            gap: 30px;
            flex-direction: column;
            .home{
                width: 100%;
            }
        }
    }
    .search-bar{
        background-color: var(--content-color);
        width: 25%;
        margin-top: 40px;
        margin-bottom: 40px;
        border-radius: 6px; 
        padding: 8px 16px;
        height: 800px;
        display: flex;
        flex-direction: column;
        align-items: center;
        input{
            padding: 8px 16px;
            font-size: 1rem;
            background-color: #B6BBC4;
            border: none;
            border-radius: 6px;
            color: #F0ECE5;
            &:focus{
                outline: none;
                color: black;
            }
        }
    }
}

</sytle>