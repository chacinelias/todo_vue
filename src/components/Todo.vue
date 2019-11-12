<template>
    <div class="container">

        <div class="row" :class="{border:submitFlag}">

            <!-- IF NOT SUBMITTED -->
            <div class="col-12" v-if="!submitFlag">
                <form @submit.prevent="submit" class="row" style="font-size: 40px; ">
                    <input style="width: 100%; font-style: italic;" v-model="text" placeholder="Add Text..." maxlength="40">
                </form>
            </div>

            <!-- IF SUBMITTED -->
            <div class="col-1" v-if="submitFlag">
                <button class="btn fa-2x"><i class="fas fa-minus"></i></button>
            </div>

            <div class="col-10" v-if="submitFlag">
                <div @click="submitFlag = !submitFlag" style="font-size: 40px">
                    <p class="vertical-center" v-if="completed"><del>{{ text }}</del></p>
                    <p class="vertical-center" v-else>{{ text }}</p>

                </div>
            </div>

            <div class="col-1" v-if="submitFlag">
                <input class="form-check-input ml-2 vertical-center" type="checkbox" v-model="completed" id="inlineCheckbox1">
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'Todo',
    data() {
        return {
            text: '',
            submitFlag: false,
            completed: false
        }
    },
    methods: {
        submit(){
            this.submitFlag = !this.submitFlag;
        }
    }
}
</script>

<style scoped>
    .vertical-center {
        margin: 0;
        position: absolute;
        top: 50%;
        -ms-transform: translateY(-50%);
        transform: translateY(-50%);
    }
</style>