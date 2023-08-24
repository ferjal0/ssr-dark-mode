<script>
	import { enhance } from '$app/forms'
	import { page } from '$app/stores'

	const submitUpdateTheme = ({ action }) => {
		const theme = action.searchParams.get('theme')

		if (theme) {
			document.documentElement.setAttribute('data-theme', theme)
		}
	}
</script>

<div class="grid h-screen w-screen place-items-start p-4">
	<form method="POST" use:enhance={submitUpdateTheme} class="flex flex-col gap-4">
		<button formaction="/?/setTheme&theme=light&redirectTo={$page.url.pathname}" class="btn">
			Light
		</button>
		<button formaction="/?/setTheme&theme=dark&redirectTo={$page.url.pathname}" class="btn">
			Dark
		</button>
	</form>
</div>
