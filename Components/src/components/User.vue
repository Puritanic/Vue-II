<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
		<button @click="changeName">Change name</button>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :myName="name" :userAge="age" :resetName='resetName' @nameReset="name = $event"></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :userAge="age" @addAge="age = $event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
import UserDetail from './UserDetail.vue';
import UserEdit from './UserEdit.vue';

export default {
	data() {
		return {
			name: 'Darko',
			age: 28,
		};
	},
	methods: {
		changeName() {
			this.name = 'DarkoOoOoO';
		},
		resetName() {
			this.name = 'Darko';
		},
	},
	components: {
		appUserDetail: UserDetail,
		appUserEdit: UserEdit,
	},
};
</script>

<style scoped>
div {
	background-color: lightblue;
}
</style>
