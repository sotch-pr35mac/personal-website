<script>
export let color = 'white';
export let width = 'full-width';
export let link = false;

const getClasses = () => {
	return ['sidebar-link',
		`sidebar-link--${color}`,
		`sidebar-link--${width}`].join(' ');
}

const navigate = slug => {
    if (link)
        document.location.href = `${document.location.href.split('#')[0]}#${slug}`;
}
</script>

<style>
.sidebar-link {
	margin: var(--space);
	padding: var(--space--large);
	border: none;
	cursor: pointer;
	color: var(--text-color--light);
	font-family: var(--font--text);
	text-align: left;
	font-size: 1em;
	border-radius: var(--border-radius);
}
.sidebar-link--white {
	background-color: var(--color--white);
}
.sidebar-link--grey {
	background-color: var(--color--grey);
}
.sidebar-link--full-width {
	width: 100%;
}
.sidebar-link--fit-content {
	width: fit-content;
}
.sidebar-link:hover {
	box-shadow: var(--shadow);
	color: var(--color--black);
	transition-property: box-shadow, color;
	transition-duration: 0.25s;
}
</style>

<button class="{getClasses()}" on:click={() => navigate(link)}>
	<slot></slot>
</button>
