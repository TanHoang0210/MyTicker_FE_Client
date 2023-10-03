<template>
    <header class="header" >
        <div class="left-header">
            <router-link style="text-decoration: none; color: inherit;"  class="left-header--logo" to="/">
                <img src="https://i.ibb.co/VQGNx7z/Logo.png" alt="">
            </router-link>
            <div class="left-header--control">
        <b-nav class="left-header--list">
            <b-nav-item class="left-header--item">Sự Kiện</b-nav-item>
            <b-nav-item class="left-header--item">Thể Loại</b-nav-item>
            <b-nav-item class="left-header--item">Địa Điểm</b-nav-item>
            <b-nav-item class="left-header--item">Về Chúng Tôi</b-nav-item>
        </b-nav>
        </div>
        </div>
        <div class="right-header">
            <div class="header-search">
                <div class="header-search--item">
                    <router-link class="header-search--link"
                             to="/about">
                    <button class="header-search--button">
                        <svg xmlns="http://www.w3.org/2000/svg" class="header-search--icon" height="1em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"/></svg>
                    </button>
                    </router-link>
                    <b-form-input class="header-search--input" v-model="text" placeholder="Tìm Kiếm Sự kiện"></b-form-input>
                </div>
            </div>
            <div class="user-control">
                <router-link class="register-link" style="text-decoration: none; color: inherit;" to="/about">
                        <b-icon icon="person-fill"></b-icon>
                        Đăng Nhập/Đăng Ký
                </router-link>
            </div>
            <div class="language-control">
                <div class="language-control--item">
                    <img class="language-type" src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTI0IDIwQzI0IDIwLjU1MjUgMjMuNTUyNSAyMSAyMyAyMUgxQzAuNDQ3NSAyMSAwIDIwLjU1MjUgMCAyMFY0QzAgMy40NDc1IDAuNDQ3NSAzIDEgM0gyM0MyMy41NTI1IDMgMjQgMy40NDc1IDI0IDRWMjBaIiBmaWxsPSIjRDgyODI3Ii8+CjxwYXRoIGQ9Ik0xNi4xODAzIDEwLjUyMDdIMTMuMjM0OEwxMS45OTk4IDcuODQyMTZMMTAuNzYzMyAxMC41MjA3SDcuODE4ODVMOS45NzAzNSAxMi43NDcyTDkuMTc1MzUgMTUuOTczN0wxMS45OTk4IDE0LjM2OTJMMTQuODIzOCAxNS45NzM3TDE0LjAyODggMTIuNzQ3MkwxNi4xODAzIDEwLjUyMDdaIiBmaWxsPSIjRkZGRDM4Ii8+Cjwvc3ZnPgo=" alt="">
                </div>
                <div class="language-choice">
                    <div class="language-choice--item" v-on:click="myLanguage" v-bind:class="{ active: isActive }" >
                        <img class="language-type language-type-item " src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHBhdGggZD0iTTI0IDIwQzI0IDIwLjU1MjUgMjMuNTUyNSAyMSAyMyAyMUgxQzAuNDQ3NSAyMSAwIDIwLjU1MjUgMCAyMFY0QzAgMy40NDc1IDAuNDQ3NSAzIDEgM0gyM0MyMy41NTI1IDMgMjQgMy40NDc1IDI0IDRWMjBaIiBmaWxsPSIjRDgyODI3Ii8+CjxwYXRoIGQ9Ik0xNi4xODAzIDEwLjUyMDdIMTMuMjM0OEwxMS45OTk4IDcuODQyMTZMMTAuNzYzMyAxMC41MjA3SDcuODE4ODVMOS45NzAzNSAxMi43NDcyTDkuMTc1MzUgMTUuOTczN0wxMS45OTk4IDE0LjM2OTJMMTQuODIzOCAxNS45NzM3TDE0LjAyODggMTIuNzQ3MkwxNi4xODAzIDEwLjUyMDdaIiBmaWxsPSIjRkZGRDM4Ii8+Cjwvc3ZnPgo=" alt="">
                        <span class="language-name ">Tiếng Việt</span>
                    </div>
                    <!-- <div class="language-choice--item" v-on:click="myLanguage" v-bind:class="{ active: isActive }">
                        <img class="language-type language-type-item" src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9Im5vIj8+DQo8IS0tIENyZWF0ZWQgd2l0aCBTb2RpcG9kaSAoImh0dHA6Ly93d3cuc29kaXBvZGkuY29tLyIpIC0tPg0KPCEtLSAvQ3JlYXRpdmUgQ29tbW9ucyBQdWJsaWMgRG9tYWluIC0tPg0KPCEtLQ0KDQo8cmRmOlJERiB4bWxucz0iaHR0cDovL3dlYi5yZXNvdXJjZS5vcmcvY2MvIg0KICAgICB4bWxuczpkYz0iaHR0cDovL3B1cmwub3JnL2RjL2VsZW1lbnRzLzEuMS8iDQogICAgIHhtbG5zOnJkZj0iaHR0cDovL3d3dy53My5vcmcvMTk5OS8wMi8yMi1yZGYtc3ludGF4LW5zIyI+DQo8V29yayByZGY6YWJvdXQ9IiI+DQogICAgPGRjOnRpdGxlPk5ldyBaZWFsYW5kLCBBdXN0cmFsaWEsIFVuaXRlZCBLaW5nZG9tLCBVbml0ZWQgU3RhdGVzLCANCkJvc25pYSBhbmQgSGVyemVnb3ZpbmEsIEF6ZXJiYWlqYW4sIEFybWVuaWEsIEJhaGFtYXMsIEJlbGdpdW0sIEJlbmluLCANCkJ1bGdhcmlhLCBFc3RvbmlhLCBGaW5sYW5kLCBHYWJvbiwgR2FtYmlhLCBHZXJtYW55LCBHcmVlY2UsIEdyZWVubGFuZCwgDQpHdWluZWEsIEhvbmR1cmFzLCBJc3JhZWwsIEphbWFpY2EsIEpvcmRhbiwgYW5kIFJvbWFuaWEgRmxhZ3M8L2RjOnRpdGxlPg0KICAgIDxkYzpyaWdodHM+PEFnZW50Pg0KICAgICAgIDxkYzp0aXRsZT5EYW5pZWwgTWNSYWU8L2RjOnRpdGxlPg0KICAgIDwvQWdlbnQ+PC9kYzpyaWdodHM+DQogICAgPGxpY2Vuc2UgcmRmOnJlc291cmNlPSJodHRwOi8vd2ViLnJlc291cmNlLm9yZy9jYy9QdWJsaWNEb21haW4iIC8+DQo8L1dvcms+DQoNCjxMaWNlbnNlIHJkZjphYm91dD0iaHR0cDovL3dlYi5yZXNvdXJjZS5vcmcvY2MvUHVibGljRG9tYWluIj4NCiAgICA8cGVybWl0cyByZGY6cmVzb3VyY2U9Imh0dHA6Ly93ZWIucmVzb3VyY2Uub3JnL2NjL1JlcHJvZHVjdGlvbiIgLz4NCiAgICA8cGVybWl0cyByZGY6cmVzb3VyY2U9Imh0dHA6Ly93ZWIucmVzb3VyY2Uub3JnL2NjL0Rpc3RyaWJ1dGlvbiIgLz4NCiAgICA8cGVybWl0cyByZGY6cmVzb3VyY2U9Imh0dHA6Ly93ZWIucmVzb3VyY2Uub3JnL2NjL0Rlcml2YXRpdmVXb3JrcyIgLz4NCjwvTGljZW5zZT4NCjwvcmRmOlJERj4NCi0tPg0KPHN2ZyBpZD0ic3ZnMSIgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iNDgwIiB3aWR0aD0iNjQwIiB2ZXJzaW9uPSIxLjEiIHhtbG5zOmNjPSJodHRwOi8vY3JlYXRpdmVjb21tb25zLm9yZy9ucyMiIHhtbG5zOmRjPSJodHRwOi8vcHVybC5vcmcvZGMvZWxlbWVudHMvMS4xLyI+DQogPG1ldGFkYXRhIGlkPSJtZXRhZGF0YTI5OTUiPg0KICA8cmRmOlJERj4NCiAgIDxjYzpXb3JrIHJkZjphYm91dD0iIj4NCiAgICA8ZGM6Zm9ybWF0PmltYWdlL3N2Zyt4bWw8L2RjOmZvcm1hdD4NCiAgICA8ZGM6dHlwZSByZGY6cmVzb3VyY2U9Imh0dHA6Ly9wdXJsLm9yZy9kYy9kY21pdHlwZS9TdGlsbEltYWdlIi8+DQogICA8L2NjOldvcms+DQogIDwvcmRmOlJERj4NCiA8L21ldGFkYXRhPg0KIDxkZWZzIGlkPSJkZWZzMyI+DQogIDxjbGlwUGF0aCBpZD0iY2xpcFBhdGg4NjczIiBjbGlwUGF0aFVuaXRzPSJ1c2VyU3BhY2VPblVzZSI+DQogICA8cmVjdCBpZD0icmVjdDg2NzUiIGZpbGwtb3BhY2l0eT0iMC42NyIgaGVpZ2h0PSI1MTIiIHdpZHRoPSI2ODIuNjciIHk9Ii0uMDAwMDAyODYxMyIgeD0iLTg1LjMzMyIvPg0KICA8L2NsaXBQYXRoPg0KIDwvZGVmcz4NCiA8ZyBpZD0iZmxhZyIgY2xpcC1wYXRoPSJ1cmwoI2NsaXBQYXRoODY3MykiIHRyYW5zZm9ybT0ibWF0cml4KC45Mzc1MCAwIDAgLjkzNzUwIDgwIC4wMDAwMDI2ODI1KSI+DQogIDxnIGlkPSJnNTc4IiBzdHJva2Utd2lkdGg9IjFwdCIgdHJhbnNmb3JtPSJtYXRyaXgoMTcuMDY3IDAgMCAxNy4wNjcgLTI1NiAtMC4wMDAwMDI0KSI+DQogICA8cmVjdCBpZD0icmVjdDEyNCIgaGVpZ2h0PSIzMCIgd2lkdGg9IjYwIiB5PSIwIiB4PSIwIiBmaWxsPSIjMDA2Ii8+DQogICA8ZyBpZD0iZzU4NCI+DQogICAgPHBhdGggaWQ9InBhdGgxNDYiIGQ9Im0wIDB2My4zNTQxbDUzLjI5MiAyNi42NDZoNi43MDh2LTMuMzU0bC01My4yOTItMjYuNjQ2aC02LjcwOHptNjAgMHYzLjM1NGwtNTMuMjkyIDI2LjY0NmgtNi43MDh2LTMuMzU0bDUzLjI5Mi0yNi42NDZoNi43MDh6IiBmaWxsPSIjZmZmIi8+DQogICAgPHBhdGggaWQ9InBhdGgxMzYiIGQ9Im0yNSAwdjMwaDEwdi0zMGgtMTB6bS0yNSAxMHYxMGg2MHYtMTBoLTYweiIgZmlsbD0iI2ZmZiIvPg0KICAgIDxwYXRoIGlkPSJwYXRoMTQxIiBkPSJtMCAxMnY2aDYwdi02aC02MHptMjctMTJ2MzBoNnYtMzBoLTZ6IiBmaWxsPSIjYzAwIi8+DQogICAgPHBhdGggaWQ9InBhdGgxNTAiIGQ9Im0wIDMwIDIwLTEwaDQuNDcybC0yMCAxMGgtNC40NzJ6bTAtMzAgMjAgMTBoLTQuNDcybC0xNS41MjgtNy43NjM5di0yLjIzNjF6bTM1LjUyOCAxMCAyMC0xMGg0LjQ3MmwtMjAgMTBoLTQuNDcyem0yNC40NzIgMjAtMjAtMTBoNC40NzJsMTUuNTI4IDcuNzY0djIuMjM2eiIgZmlsbD0iI2MwMCIvPg0KICAgPC9nPg0KICA8L2c+DQogPC9nPg0KPC9zdmc+DQo=" alt="">
                        <span class="language-name">Tiếng Anh</span>
                    </div> -->
                </div>
            </div>
        </div>
    </header>
  </template>
  
  <script>
    export default {
    name: 'Header',
    data: () => {
      return {
        isActive: false
      }
    },
    methods: {
        myLanguage: function() {
      this.isActive = !this.isActive;
      // some code to filter users
    }
    }
    }
  </script>
  <style scoped lang="scss">
  .header{
     display: flex;
     -webkit-box-align: center;
     align-items: center;
     z-index: 2;
     width: 100%;
     height: 102px;
     background-color: var(--primary-color);
     padding-left: 32px;
     padding-right: 32px;
     justify-content: space-evenly;
     top: 0px;
  }
  //left-header
  .left-header{
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    height: 100%;
  }
  .left-header--logo{
    text-decoration: none;
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    margin-right: 32px;
    height: 100%;
  }
  .left-header--logo img{
    height: 50px;
  }
  .left-header--control{
    height: 100%;
    display: flex;
    align-items: center;
    flex-wrap: nowrap;
    overflow: hidden;
  }
  .left-header--control ul{
    height: 100%;
  }
  .left-header--control ul li{
    display: flex;
    height: 100%;
    text-align: center;
    align-items: center;
  }
  .left-header--control ul li a{
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    color: var(--text-color);
    font-size: 1.2rem;
    font-weight: 600;
    line-height: 50px;
  }
  .left-header--control ul li a:hover{
        background-color: rgb(255, 255, 255,1);
  }
.header-search{
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    position: relative;
    width: 372px;
      }
    .header-search--item{
        display: flex;
        font-size: 16px;
        -webkit-box-align: center;
        align-items: center;
        position: relative;
        width: 100%;
        color: var(--text-color);
    }
    .header-search--item svg{
        fill: currentColor;
    }
    .header-search--input{
    color: var(--text-color);
    background-color: var(--primary-color);
    line-height: 24px;
    height: 44px;
    width: 80%;
    outline: none;
    border: 1px solid transparent;
    border-radius: 4px 0px 0px 4px;
    box-shadow: none;
    border: 1px solid var(--text-color)!important;
    transition: 0.3s;
    border-right:none !important;
    }
    .header-search--link{
        position: absolute;
        right: 0;
        height: 100%;
        width: 20%;
        display: flex;
        background-color: var(--primary-color);
        border: 1px solid var(--text-color);
        border-left:none;
        border-radius: 0px 4px 4px 0px;
    }
    .header-search--button{
        border: none;
        height: 95%;
        text-align: center;
        margin: auto;
        color: var(--text-color);
        background-color: var(--primary-color);
    }
    .header-search--icon{
        width: 16px;
        height: 16px;
    }
    input::placeholder {
    color: var(--text-color) !important;
    opacity: 1;
    }
    input:focus::placeholder {
    color: var(--primary-color)!important;
    }
    .header-search--icon:hover{
        cursor: pointer;
    }

.form-control:focus{
    box-shadow: none !important;
}
    //rigth-header
.user-control{
    display: flex;
    align-items: center;
    height: 76px;
    background-color: var(--primary-color);
}
    .right-header{
    display: flex;
    align-items: center;
    margin-left: auto;
    margin-right: 0px;
    }
    .register-link{
        display: flex;
    height: 100%;
    align-items: center;
        font-style: normal;
    font-weight: normal;
    font-size: 1.2rem;
    line-height: 50px;
    padding-left: 8px;
    padding-right: 8px;
    color: var(--text-color);
    margin-left: 20px;
    }
    .register-link:hover{
            background-color: #fff;
    }
    .language-control{
        display: flex;
    -webkit-box-align: center;
    align-items: center;
    position: relative;
    margin-left: 12px;
    height: 72px;
    }
    .language-control:hover{
        cursor: pointer;
    }
    .language-control:hover .language-choice{
        display: block;
    }
    .language-control::before{
        display: block;
        content: "";
        background-color: var(--text-color);
        height: 44px;
        width: 1px;
        margin: 0 8px;
    }
    .language-control--item{
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    padding: 8px;
    }
    .language-type{
        margin-left: 8px;
        width: 24px;
    }
    .dropdown-img{
        margin-left: 8px;
        width: 8px;
    }
    .language-type-item{
        margin-right: 12px;
    }


    .language-choice{
        box-shadow: var(--text-color) 0px 1px 5px;
    border-radius: 8px;
    border: 1px var(--primary-color);
    position: absolute;
    top: 64px;
    right: -28px;
    z-index: 1;
    background: var(--primary-color);
    width: 160px;
    display: none;
    cursor: auto;
    font-style: normal;
    font-size: 1.2rem;
    line-height: 20px;
    }
    .language-choice--item{
        display: flex;
    -webkit-box-align: center;
    align-items: center;
    padding: 8px;
    cursor: pointer;
    }
    .active{
        font-weight: bold;
    }

    @media only screen and (max-width: 768px) { 
        .right-header{
            display: none;
        }
        .left-header{
            width: 100%;
        }
        .header{
            height: 65px;
        }
    }
  </style>