<template>
    <nav class="navbar orange lighten-1">
        <div class="nav-wrapper">
            <div class="navbar-left">
                
                <span class="black-text">{{ timestamp  }}</span>
            </div>

            <ul class="right hide-on-small-and-down">
                <li>
                    <a
                        class="dropdown-trigger black-text"
                        href="#"
                        data-target="dropdown"
                        ref="dropdown"
                    >
                        USER NAME
                        <i class="material-icons right">arrow_drop_down</i>
                    </a>
    
                    <ul id='dropdown' class='dropdown-content'>
                        <li>
                            <router-link to="/profile" class="black-text">
                                <i class="material-icons">account_circle</i>Профиль
                            </router-link>
                        </li>
                        <li class="divider" tabindex="-1"></li>
                        <li>
                            <a href="#" class="black-text" @click.prevent="logOut">
                                <i class="material-icons">assignment_return</i>Выйти
                            </a>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
import M from 'materialize-css' 

export default{
    data: () => ({
        // date: new Date,
        timestamp: "",
        interval: null,
        dropdown: null,
        mounth: ['января', 'февраля', 'матра','апреля', 'мая', 'июня', 'июля', 'августа','сентября', 'октяюря', 'ноября', 'декабря']
    }),
    methods: {
        logOut(){
            this.$router.push('/login?message=logout')
        },
        getNow() {
            const today = new Date();
            const month = today.getMonth()
            const date = today.getDate() + ' ' + this.mounth[month]+ ' ' + today.getFullYear();
            const time = today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds();
            const dateTime = date +' '+ time;
            this.timestamp = dateTime;
        }
        // formatedDate: d => d.toLocaleString('ru-RU').replace(',', '').slice(0, -3) только время
    },
    
    created() {
        setInterval(this.getNow, 1000);
    },
    mounted() {
        this.interval = setInterval (() => {
            this.date = new Date()
        }, 1000)
        this.dropdown = M.Dropdown.init(this.$refs.dropdown, {
            constrainWidth: true
        })
    },
    beforeUnmount() {
        clearInterval(this.interval)
        if (this.dropdown && this.dropdown.destroy){
            this.dropdown.destroy()
        }
    }
}

</script>

