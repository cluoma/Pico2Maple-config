<script>
</script>

<div class="container">
	<h1 class="text-3xl font-bold mb-6">Pico2Maple Controller Mapper</h1>
	<div style="padding-bottom: 1rem;"><a href="/">Mapper</a> | How-to</div>
	<div style="padding-bottom: 1rem;">Compatible Firmware: pico2maple(-w)_2025-06-14.uf2</div>
	<div class="card">
		<h2>How to Use</h2>
		<p>Set up your desired controller layout by using the dropdowns to select which buttons on a standard Xbox-gamepad layout should map to the given Dreamcast button.</p>
		<p>Clicking the 'Download Mapping' button will trigger the download of a small binary file for the desired controller layout.</p>
		<p>While Pico2Maple is in BOOTSEL mode, use <a href="https://github.com/raspberrypi/picotool">picotool</a> to load the mapping onto the device using the following command:</p>
		<pre>
			picotool load "pico2maple-mapping.bin" -o 0x103FC000
		</pre>
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