<script>

	import { base } from '$app/paths';
	import { text } from '@sveltejs/kit';

	const allButtons = [
		{id: -1, 	name: "", 							cfgname: ""},
		{id: 0, 	name: "A", 							cfgname: "A"},
		{id: 1, 	name: "B", 							cfgname: "B"},
		{id: 2, 	name: "C", 							cfgname: "C"},
		{id: 3, 	name: "D", 							cfgname: "D"},
		{id: 4, 	name: "X", 							cfgname: "X"},
		{id: 5, 	name: "Y", 							cfgname: "Y"},
		{id: 6, 	name: "Z", 							cfgname: "Z"},
		{id: 7, 	name: "Start", 					cfgname: "START"},
		{id: 8, 	name: "Left Bumper", 		cfgname: "LB"},
		{id: 9, 	name: "Right Bumper", 	cfgname: "RB"},
		{id: 10, 	name: "Dpad Up", 				cfgname: "DPAD_UP"},
		{id: 11, 	name: "Dpad Down", 			cfgname: "DPAD_DOWN"},
		{id: 12, 	name: "Dpad Left", 			cfgname: "DPAD_LEFT"},
		{id: 13, 	name: "Dpad Right", 		cfgname: "DPAD_RIGHT"},
		{id: 14, 	name: "Dpad 2 Up", 			cfgname: "DPAD2_UP"},
		{id: 15, 	name: "Dpad 2 Down", 		cfgname: "DPAD2_DOWN"},
		{id: 16, 	name: "Dpad 2 Left", 		cfgname: "DPAD2_LEFT"},
		{id: 17, 	name: "Dpad 2 Right", 	cfgname: "DPAD2_RIGHT"},
		{id: 18, 	name: "Left Trigger", 	cfgname: "LT"},
		{id: 19, 	name: "Right Trigger", 	cfgname: "RT"},
		{id: 20, 	name: "Analog Up", 			cfgname: "A1_UP"},
		{id: 21, 	name: "Analog Down", 		cfgname: "A1_DOWN"},
		{id: 22, 	name: "Analog Left", 		cfgname: "A1_LEFT"},
		{id: 23, 	name: "Analog Right", 	cfgname: "A1_RIGHT"},
		{id: 24, 	name: "Analog 2 Up", 		cfgname: "A2_UP"},
		{id: 25, 	name: "Analog 2 Down", 	cfgname: "A2_DOWN"},
		{id: 26, 	name: "Analog 2 Left", 	cfgname: "A2_LEFT"},
		{id: 27, 	name: "Analog 2 Right", cfgname: "A2_RIGHT"}
	];

	const standardDCButtons = [
		{id: 0, 	name: "A", 							cfgname: "A"},
		{id: 1, 	name: "B", 							cfgname: "B"},
		{id: 4, 	name: "X", 							cfgname: "X"},
		{id: 5, 	name: "Y", 							cfgname: "Y"},
		{id: 7, 	name: "Start", 					cfgname: "START"},
		{id: 10, 	name: "Dpad Up", 				cfgname: "DPAD_UP"},
		{id: 11, 	name: "Dpad Down", 			cfgname: "DPAD_DOWN"},
		{id: 12, 	name: "Dpad Left", 			cfgname: "DPAD_LEFT"},
		{id: 13, 	name: "Dpad Right", 		cfgname: "DPAD_RIGHT"},
		{id: 18, 	name: "Left Trigger", 	cfgname: "LT"},
		{id: 19, 	name: "Right Trigger", 	cfgname: "RT"},
		{id: 20, 	name: "Analog Up", 			cfgname: "A1_UP"},
		{id: 21, 	name: "Analog Down", 		cfgname: "A1_DOWN"},
		{id: 22, 	name: "Analog Left", 		cfgname: "A1_LEFT"},
		{id: 23, 	name: "Analog Right", 	cfgname: "A1_RIGHT"}
	];

	const nonstandardDCButtons = [
		{id: 2, 	name: "C", 							cfgname: "C"},
		{id: 3, 	name: "D", 							cfgname: "D"},
		{id: 6, 	name: "Z", 							cfgname: "Z"},
		{id: 14, 	name: "Dpad 2 Up", 			cfgname: "DPAD2_UP"},
		{id: 15, 	name: "Dpad 2 Down", 		cfgname: "DPAD2_DOWN"},
		{id: 16, 	name: "Dpad 2 Left", 		cfgname: "DPAD2_LEFT"},
		{id: 17, 	name: "Dpad 2 Right", 	cfgname: "DPAD2_RIGHT"},
		{id: 24, 	name: "Analog 2 Up", 		cfgname: "A2_UP"},
		{id: 25, 	name: "Analog 2 Down", 	cfgname: "A2_DOWN"},
		{id: 26, 	name: "Analog 2 Left", 	cfgname: "A2_LEFT"},
		{id: 27, 	name: "Analog 2 Right", cfgname: "A2_RIGHT"}
	];

	const DCButtons = [
		//{id: -1, name: ""},
		{id: 0, 	name: "A", 							cfgname: "A"},
		{id: 1, 	name: "B", 							cfgname: "B"},
		{id: 2, 	name: "C", 							cfgname: "C"},
		{id: 3, 	name: "D", 							cfgname: "D"},
		{id: 4, 	name: "X", 							cfgname: "X"},
		{id: 5, 	name: "Y", 							cfgname: "Y"},
		{id: 6, 	name: "Z", 							cfgname: "Z"},
		{id: 7, 	name: "Start", 					cfgname: "START"},
		{id: 10, 	name: "Dpad Up", 				cfgname: "DPAD_UP"},
		{id: 11, 	name: "Dpad Down", 			cfgname: "DPAD_DOWN"},
		{id: 12, 	name: "Dpad Left", 			cfgname: "DPAD_LEFT"},
		{id: 13, 	name: "Dpad Right", 		cfgname: "DPAD_RIGHT"},
		{id: 14, 	name: "Dpad 2 Up", 			cfgname: "DPAD2_UP"},
		{id: 15, 	name: "Dpad 2 Down", 		cfgname: "DPAD2_DOWN"},
		{id: 16, 	name: "Dpad 2 Left", 		cfgname: "DPAD2_LEFT"},
		{id: 17, 	name: "Dpad 2 Right", 	cfgname: "DPAD2_RIGHT"},
		{id: 18, 	name: "Left Trigger", 	cfgname: "LT"},
		{id: 19, 	name: "Right Trigger", 	cfgname: "RT"},
		{id: 20, 	name: "Analog Up", 			cfgname: "A1_UP"},
		{id: 21, 	name: "Analog Down", 		cfgname: "A1_DOWN"},
		{id: 22, 	name: "Analog Left", 		cfgname: "A1_LEFT"},
		{id: 23, 	name: "Analog Right", 	cfgname: "A1_RIGHT"},
		{id: 24, 	name: "Analog 2 Up", 		cfgname: "A2_UP"},
		{id: 25, 	name: "Analog 2 Down", 	cfgname: "A2_DOWN"},
		{id: 26, 	name: "Analog 2 Left", 	cfgname: "A2_LEFT"},
		{id: 27, 	name: "Analog 2 Right", cfgname: "A2_RIGHT"}
	];
	const sources = [
		{id: -1, 	name: "",								cfgname: ""},
		{id: 0, 	name: "A", 							cfgname: "A"},
		{id: 1, 	name: "B", 							cfgname: "B"},
		{id: 4, 	name: "X", 							cfgname: "X"},
		{id: 5, 	name: "Y", 							cfgname: "Y"},
		{id: 7, 	name: "Start", 					cfgname: "START"},
		{id: 8, 	name: "Left Bumper", 		cfgname: "LB"},
		{id: 9, 	name: "Right Bumper", 	cfgname: "RB"},
		{id: 10, 	name: "Dpad Up", 				cfgname: "DPAD_UP"},
		{id: 11, 	name: "Dpad Down", 			cfgname: "DPAD_DOWN"},
		{id: 12, 	name: "Dpad Left", 			cfgname: "DPAD_LEFT"},
		{id: 13, 	name: "Dpad Right", 		cfgname: "DPAD_RIGHT"},
		{id: 18, 	name: "Left Trigger", 	cfgname: "LT"},
		{id: 19, 	name: "Right Trigger", 	cfgname: "RT"},
		{id: 20, 	name: "Analog Up", 			cfgname: "A1_UP"},
		{id: 21, 	name: "Analog Down", 		cfgname: "A1_DOWN"},
		{id: 22, 	name: "Analog Left", 		cfgname: "A1_LEFT"},
		{id: 23, 	name: "Analog Right", 	cfgname: "A1_RIGHT"},
		{id: 24, 	name: "Analog 2 Up", 		cfgname: "A2_UP"},
		{id: 25, 	name: "Analog 2 Down", 	cfgname: "A2_DOWN"},
		{id: 26, 	name: "Analog 2 Left", 	cfgname: "A2_LEFT"},
		{id: 27, 	name: "Analog 2 Right", cfgname: "A2_RIGHT"}
	];

	let mappingTargets = {};
	standardDCButtons.forEach(button => {
		if (button.name !== "")
			mappingTargets[button.name] = ["", "", "", ""];
	});
	nonstandardDCButtons.forEach(button => {
		if (button.name !== "")
			mappingTargets[button.name] = ["", "", "", ""];
	});

	let output = new Uint8Array(256);
	for (let i = 0; i < 256; i++) {
		output[i] = 0;
	}
	// autoload
	output[145] = 0;
	// settings set flags binary 11 says vmu and custom mapping are set
	output[146] = 3;


	function handleChange(button, index, value) {
		mappingTargets[button][index] = value;
		//console.log(JSON.stringify(mappingTargets, null, 2));
	}

	function xor8bit(a, b) {
		// Ensure numbers are within the 8-bit range (0-255)
		a = a & 0xFF;
		b = b & 0xFF;

		// Perform the XOR operation
		return a ^ b;
	}

	// options
	let optionAutoLoad = false;


	function downloadMappings() {
		const blob = new Blob([output], { type: 'application/octet-stream' });
		const url = URL.createObjectURL(blob);
		//const dataStr = "data:application/octet-stream," + encodeURIComponent(output);
		const downloadAnchor = document.createElement('a');
		downloadAnchor.setAttribute("href", url);
		downloadAnchor.setAttribute("download", "pico2maple-mapping.bin");
		document.body.appendChild(downloadAnchor);
		downloadAnchor.click();
		document.body.removeChild(downloadAnchor);
	}

	function downloadMappingsTextfile() {
		let textOutput = "# This is a Pico2Maple controller remapping file\n";
		textOutput += "# Copy it to your SD card inside a folder called 'pico2maple'\n\n";

		allButtons.forEach(function(button, index) {
			if (button.id !== -1) {
				if (standardDCButtons.map(b => b.id).includes(button.id) ||
					nonstandardDCButtons.map(b => b.id).includes(button.id)) {
					const sources = [
						allButtons.find(b => b.name === mappingTargets[button.name][0]).cfgname,
						allButtons.find(b => b.name === mappingTargets[button.name][1]).cfgname,
						allButtons.find(b => b.name === mappingTargets[button.name][2]).cfgname,
						allButtons.find(b => b.name === mappingTargets[button.name][3]).cfgname
					]
					for (let i = 0; i < 4; i++) {
						if (sources[i] !== "") {
							textOutput += sources[i] + ": " + button.cfgname + "\n";
						}
					}
				}
			}
		});

		textOutput += "\n# OPTIONS\n";

		if (optionAutoLoad) {
			textOutput += "OPTION_AUTOLOAD: TRUE\n";
		} else {
			textOutput += "OPTION_AUTOLOAD: FALSE\n";
		}

		const blob = new Blob([textOutput], { type: 'text/plain' });
		const url = URL.createObjectURL(blob);
		const downloadAnchor = document.createElement('a');
		downloadAnchor.setAttribute("href", url);
		downloadAnchor.setAttribute("download", "pico2maple_controller_map.cfg");
		document.body.appendChild(downloadAnchor);
		downloadAnchor.click();
		document.body.removeChild(downloadAnchor);
	}

	function handleSubmit(action) {
		//alert("Mappings saved: " + JSON.stringify(mappingTargets, null, 2));
		allButtons.forEach(function(button, index) {
			if (button.id !== -1) {
				output[1 + button.id*5] = button.id;
				output[1 + button.id*5 + 1] = -1;
				output[1 + button.id*5 + 2] = -1;
				output[1 + button.id*5 + 3] = -1;
				output[1 + button.id*5 + 4] = -1;

				if (standardDCButtons.map(b => b.id).includes(button.id) ||
					  nonstandardDCButtons.map(b => b.id).includes(button.id)) {
					const sources = [
						allButtons.find(b => b.name === mappingTargets[button.name][0]).id,
						allButtons.find(b => b.name === mappingTargets[button.name][1]).id,
						allButtons.find(b => b.name === mappingTargets[button.name][2]).id,
						allButtons.find(b => b.name === mappingTargets[button.name][3]).id
					]
					let sourceCount = 0;
					for (let i = 0; i < 4; i++) {
						if (sources[i] !== -1) {
							output[1 + button.id * 5 + 1 + sourceCount] = sources[i];
							sourceCount++;
						}
					}
				}

			}
		});

		// check autoload
		if (optionAutoLoad) {
			output[145] = 1;
		} else {
			output[145] = 0;
		}

		let crc = 0b10101010;
		for (let i = 0; i < 255; i++) {
			crc = xor8bit(crc, output[i]);
		}
		output[255] = crc;

		//alert(output);
		console.log("Triggered action:", action);
		if (action === "binary") {
			downloadMappings();
		} else if (action === "textfile") {
			downloadMappingsTextfile();
		}
	}
</script>

<div class="container">
	<h1 class="text-3xl font-bold mb-6">Pico2Maple Controller Mapper</h1>
	<div style="padding-bottom: 1rem;">Mapper | <a href="{base}/about">How-to Use</a></div>
	<div style="padding-bottom: 1rem;">Minimum Compatible Firmware: pico2maple(-w)_2025-06-14</div>
	<div class="card">
		<form on:submit|preventDefault={handleSubmit('default')}>
			<div class="header-row">
				<div>Target Dreamcast Button</div>
				<div>Source Gamepad Buttons</div>
			</div>

			<div class="form-group">
			<!-- -->
			{#each standardDCButtons as button (button.id)}
					<label for={button.name}>{button.name}</label>
					<div class="select-row">
						{#each [0, 1, 2, 3] as i}
							<select
								class="select"
								bind:value={mappingTargets[button.name][i]}
								on:change={(e) => handleChange(button.name, i, e.target.value)}
							>
								{#each sources as source (source.id)}
									<option value={source.name}>{source.name}</option>
								{/each}
							</select>
						{/each}
					</div>
			{/each}
			</div>

			<div class="highlighted-content">
				<div class="highlighted-content-title">Non-Standard Buttons</div>
				<div class="form-group">
					<!-- -->
					{#each nonstandardDCButtons as button (button.id)}
						<label for={button.name}>{button.name}</label>
						<div class="select-row">
							{#each [0, 1, 2, 3] as i}
								<select
									class="select"
									bind:value={mappingTargets[button.name][i]}
									on:change={(e) => handleChange(button.name, i, e.target.value)}
								>
									{#each sources as source (source.id)}
										<option value={source.name}>{source.name}</option>
									{/each}
								</select>
							{/each}
						</div>
					{/each}
				</div>
			</div>

			<div class="highlighted-content">
				<div class="highlighted-content-title">Options</div>
				<div class="form-group">
					<label>Auto-Load</label>
						<div class="select-row">
								<input
									type="checkbox"
									bind:checked={optionAutoLoad}
								>
						</div>
				</div>
			</div>

			<button type="submit" class="button" on:click={() => handleSubmit('binary')}>Download Mapping for Picotool Upload</button>
			<button type="submit" class="button" on:click={() => handleSubmit('textfile')}>Download Mapping for microSD Card</button>
		</form>
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
    form {
        display: grid;
        gap: 0.5rem;
    }
    .header-row {
        display: grid;
        grid-template-columns: 1.5fr 4fr;
        font-weight: bold;
        padding-bottom: 0.5rem;
        border-bottom: 1px solid #ccc;
    }
    .form-group {
        display: grid;
        grid-template-columns: 1.5fr 4fr;
        align-items: center;
        gap: 0.5rem;
    }
    .select-row {
        display: flex;
        gap: 0.5rem;
    }
    .select {
        padding: 0.5rem;
        border: 1px solid #ccc;
        border-radius: 0.5rem;
        flex: 1;
    }
    .button {
        width: 100%;
        margin-top: 1rem;
        padding: 0.75rem;
        background-color: #1a202c;
        color: white;
        border: none;
        border-radius: 0.5rem;
        cursor: pointer;
    }
    .highlighted-content {
        background-color: #eeeeee;
        padding: 1rem;
        border-radius: 1rem;
    }
    .highlighted-content-title {
        padding: 0.5rem;
				padding-top: 0;
				font-weight: bold;
    }
    .collapsible-content {
        margin-top: 1rem;
        padding: 1rem;
        background-color: #edf2f7;
        border-radius: 0.5rem;
    }
    .collapse-toggle {
        width: 35%;
				text-align: center;
        margin-top: 1rem;
        padding: 0.25rem;
        background-color: #1a202c;
        color: white;
        border: none;
        border-radius: 0.5rem;
        cursor: pointer;
    }
    .collapse-toggle:hover {
        text-decoration: none;
    }
</style>