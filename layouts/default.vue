<template>
	<div class="page-container">
		<Header />
		<Nuxt />
	</div>
</template>

<style>
	html {
		font-family: 'Source Sans Pro',
		-apple-system,
		BlinkMacSystemFont,
		'Segoe UI',
		Roboto,
		'Helvetica Neue',
		Arial,
		sans-serif;
		font-size: 16px;
		word-spacing: 1px;
		-ms-text-size-adjust: 100%;
		-webkit-text-size-adjust: 100%;
		-moz-osx-font-smoothing: grayscale;
		-webkit-font-smoothing: antialiased;
		box-sizing: border-box;
	}

	.card {
		box-shadow: 0 0 46px 5px rgba(0,0,0,0.29);
		border-radius: .6rem;
	}

	.page-container {
		margin-bottom: 2rem;
	}

	:root {
		--accent-color: #46ad91;
	}

	.text-accent {
		color: var(--accent-color);
	}

	.text-strong {
		font-weight: 500;
		font-size: 1.5rem;
	}
</style>
