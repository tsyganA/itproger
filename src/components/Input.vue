<template>
    <input min="0" type="number" @input="changeAmount($event.target.value)" placeholder="Введите число" />
    <div>
        <button @click="convert()">Конвертировать</button>
        <button @click="favourite()" className="fav-button">В избранное</button>
    </div>
</template>

<script>
export default {
    props: {
        changeAmount: {
            type: Function,
            required: true,
        },
        convert: {
            type: Function,
            required: true,
        },
        favourite: {
            type: Function,
            required: true,
        },
    },
};
</script>

<style scoped>
input {
    outline: none;
    width: 500px;
    position: relative;
    top: -50px;
    font-size: 1.2em;
    border-radius: 3px;
    border: 0;
    padding: 10px 15px;
    background: #fafafa;
    color: #333;
}

button {
    position: relative;
    top: -20px;
    padding: 15px 20px;
    color: #fff;
    text-transform: uppercase;
    cursor: pointer;
    background: #1a032d;
    border: 0;
    border-radius: 3px;
    transition: transform 500ms ease;
}

button:hover {
    transform: scale(1.1);
}

button.fav-button {
    margin-left: 20px;
}
</style>
