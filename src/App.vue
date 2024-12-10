<template>
    <input type="text" v-model="userName" placeholder="Имя" />
    <input type="password" v-model="userPass" placeholder="Пароль" />
    <input type="email" v-model="userEmail" placeholder="Email" />
    <p className="error">{{ error }}</p>
    <button @click="sendData()">Отправить</button>
    <p>{{ users }}</p>

    <div v-if="users.length == 0">У нас нет пользователей</div>
    <div v-else-if="users.length == 1">User has 1 element</div>
    <div v-else>Users has more 1 element</div>

    <User v-for="(el, index) in users" :key="index" :user="el" :index="index" :deleteUser="deleteUser" />
</template>

<script>
import User from './components/User.vue';

export default {
    components: { User },
    data() {
        return {
            users: [],
            error: '',
            userName: '',
            userPass: '',
            userEmail: '',
        };
    },
    methods: {
        sendData() {
            if (this.userName == '') {
                this.error = 'Имя не введено';
                return;
            } else if (this.userEmail == '') {
                this.error = 'Email не введен';
                return;
            } else if (this.userPass == '') {
                this.error = 'Pass не введен';
                return;
            }

            this.error = '';

            this.users.push({
                name: this.userName,
                pass: this.userPass,
                email: this.userEmail,
            });
        },
        methods: {
            sendData() {},
        },
        deleteUser(index) {
            this.users.splice(index, 1);
        },
    },
};
</script>

<style scoped></style>
