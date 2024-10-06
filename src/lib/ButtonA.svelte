<script>
	export let btnLink = '#';
	export let btnText = 'Button text';
	export let btnLabel = 'Enter Aria-Label';
</script>

<a href="{btnLink}" aria-label="{btnLabel}">{btnText}</a>

<style>
    a {
        position: relative;
        z-index: 1;
        border: 1px solid var(--nightblue-color);
        padding: .75rem;
        background-color: var(--white-color);
        border-radius: 10px;
        color: var(--nightblue-color);
        font-weight: 700;
        text-decoration: none;
    }

    a:hover {
        right: 1px;
        top: 1px;
    }

    a::after {
        content: "";
        z-index: -1;
        position: absolute;
        width: 100%;
        height: 100%;
        border: 1px solid var(--nightblue-color);
        background-color: var(--white-color);
        border-radius: 10px;
        color: var(--nightblue-color);
        right: 2px;
        top: 2px;
    }

    a:hover::after {
        right: 1px;
        top: 1px;
    }
</style>