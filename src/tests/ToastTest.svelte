<script lang="ts" module>
	type ToastFn = (t: typeof toast) => void;

	export type ToastTestProps = {
		cb: ToastFn;
	};
</script>

<script lang="ts">
	import { Toaster, toast } from '$lib';

	type $$Props = ToastTestProps;

	interface Props {
		cb: $$Props['cb'];
	}

	let { cb }: Props = $props();

	function onClick() {
		cb(toast);
	}
</script>

<Toaster />

<button data-testid="trigger" onclick={onClick}>Trigger</button>
