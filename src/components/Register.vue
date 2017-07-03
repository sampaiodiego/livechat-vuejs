<template>
	<div class="livechat-form">
		<div class="error error-color error-background">
			<span>{{error}}</span>
		</div>

		<p class="welcome">
			{{welcomeMessage}}
		</p>
		<form id="livechat-registration" v-on:submit.prevent="register">
			<input type="text" name="name" id="guestName" placeholder="Name">
			<input type="email" name="email" id="guestEmail" placeholder="Email">

			<select v-if="showDepartments" name="department">
        <option value="">Select_a_department</option>
        <!--{{#each departments}}
          <option value="{{_id}}" selected="{{selectedDepartment}}">{{name}}</option>
        {{/each}}-->
      </select>
			<button type="submit" id="btnEntrar" class="button">Start_Chat</button>

			<template v-if="videoCallEnabled">
				<br>
				<button type="submit" class="button request-video">Request_video_chat</button>
			</template>
		</form>
	</div>
</template>

<script>
import router from '../router'

export default {
  components: {
  },
  data () {
    return {
      showDepartments: true,
      welcomeMessage: 'Hello',
      error: 'Hello',
      videoCallEnabled: false
    }
  },
  methods: {
    register () {
      router.push({ name: 'Messages' })
    }
  }
}
</script>

