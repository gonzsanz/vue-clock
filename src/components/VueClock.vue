<template>
    <div class="border">
        <div class="screen" :style="{ color: theme }">
            <div class="hours">{{ hour }}</div>
            <div class="dots">:</div>
            <div class="minutes">{{ minute }}</div>
            <div class="dots">:</div>
            <div class="seconds">{{ second }}</div>
            <div class="amPm">{{ amPm }}</div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'VueClock',
    props: {
        theme: {
            type: String,
        }
    },
    data() {
        return {
            hour: '--',
            minute: '--',
            second: '--',
            amPm: '--'
        }
    },
    mounted() {
        this.getTime();
    },
    methods: {
        getTime() {
            setInterval(() => {
                const date = new Date();
                this.hour = date.getHours().toString().padStart(2, '0');
                this.minute = date.getMinutes().toString().padStart(2, '0');
                this.second = date.getSeconds().toString().padStart(2, '0');
                this.amPm = this.hour >= 12 ? 'PM' : 'AM';
            }, 1000);
        }
    }
}
</script>

<style scoped>
.border {
    background-color: #666;
    width: 600px;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 10px;
}

.screen {
    font-family: 'Orbitron', sans-serif;
    background-color: #000;
    width: 550px;
    height: 120px;
    border-radius: 10px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    font-size: 70px;
    box-shadow: 0 0 5px #000;
}

.amPm {
    margin: 20px;
    font-size: 20px;
}
</style>