<script lang="ts">
	import { _ } from "svelte-i18n";

	export let type: "video" | "image" | "audio" | "file" | "csv" = "file";

	const defs = {
		image: "interface.drop_image",
		video: "interface.drop_video",
		audio: "interface.drop_audio",
		file: "interface.drop_file",
		csv: "interface.drop_csv"
	};
</script>

<div class="wrap">
	{$_(defs[type])}
	<span class="or">- or -</span>
	{$_("interface.click_to_upload")}
</div>

<style>
	.wrap {
		display: flex;
		flex-direction: column;
		justify-content: center;
		min-height: var(--size-60);
		color: var(--color-text-label);
		line-height: var(--line-md);
	}

	.or {
		color: var(--color-text-subdued);
	}

	@media (--screen-md) {
		.wrap {
			font-size: var(--scale-0);
		}
	}
</style>
