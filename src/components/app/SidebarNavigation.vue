<template>
    <ul class="sidenav app-sidenav open">
        <li>
        <router-link
        v-for="link in links"
        :key="link.url"
        active-class="active"
        :to="link.url"
        >
        <a href="#" class="waves-effect waves-orange pointer">{{ link.title  }}</a>
        </router-link></li>

    </ul>
</template>

<script>
export default{
    data: () => ({
        links: [
            {title: 'Счет', url: '/'},
            {title: 'История', url: '/history'},
            {title: 'Планирование', url: '/planing'},
            {title: 'Новая запись', url: '/record'},
            {title: 'Категории', url: '/categories'}
        ]
    })
}
</script>