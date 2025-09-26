<script>
	import { base } from '$app/paths';
</script>

<div class="container">
	<h1 class="text-3xl font-bold mb-6">Pico2Maple Controller Mapper</h1>
	<div style="padding-bottom: 1rem;"><a href="{base}/">Mapper</a> | How-to Use</div>
	<div style="padding-bottom: 1rem;">Minimum Compatible Firmware: pico2maple(-w)_2025-06-14</div>
	<div class="card">
		<h2>How to Use</h2>

		<p>Set up your desired controller layout by using the dropdowns to select which buttons on a standard Xbox-gamepad layout should map to the given Dreamcast button.</p>
		<p>Click the desired download button for either picotool upload or for a microSD card.</p>

		<h3>microSD Card</h3>
		<p>Save the controller mapping config file to the 'pico2maple' folder on your Pico2Maple's SD card.</p>

		<h3>Picotool Upload</h3>
		<p>While Pico2Maple is in BOOTSEL mode, use <a href="https://github.com/raspberrypi/picotool">picotool</a> to load the mapping onto the device using the following command:</p>
		<pre>
			picotool load "pico2maple-mapping.bin" -o 0x103FC000
		</pre>
		<p>Precompiled <a href="https://github.com/raspberrypi/pico-sdk-tools">picotool binaries</a> are also available.</p>
	</div>
</div>

<style>
    .container {
        min-height: 100vh;
        background-color: #f7fafc;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 1.5rem;
    }
    .card {
        width: 100%;
        max-width: 50rem;
        background: white;
        padding: 1rem;
        border-radius: 1rem;
        box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
    }
</style>