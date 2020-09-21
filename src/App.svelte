<script>
  // export let name;

import router from "page";
import Home from './routes/Home.svelte';
import About from './routes/About.svelte';
import Blog from './routes/Blog.svelte'
import SingleBlog from './routes/SingleBlog.svelte'

let page
let params
router('/', () => page = Home);
router('/blog', () => (page = Blog))
router('/about', () => (page = About))

router(
  '/blog/:id',

  (ctx, next) => {
    params = ctx.params
    next()
  },

  () => (page = SingleBlog)
)


router.start();
</script>


<nav class="stroke">
	<ul>
  <li>
	<a href="/">Home</a>
  </li>
  <li>
  <a href="/blog">Blog</a>
  </li>
    <li>
  <a href="/about">About</a>
  </li>

  </ul>
</nav>

<main>
  <svelte:component this="{page}" params="{params}" />

</main>

<style>
	
	 nav {
        background: linear-gradient(to right bottom, #dedbfdc7, #787e79bb);
        box-sizing: border-box;
        display: block;
        box-shadow: 0px 2px 4px black;
        margin-bottom: -0.9rem;
    }
    ul {
        list-style-type: none;
    }
    ul li {
        display: inline-flex;
        padding: 1em;
    }
    nav ul li a,
nav ul li a:after,
nav ul li a:before {
  transition: all .2s;
}
    /* ul::after {
        content: '';
    } */
    nav.stroke ul li a,
nav.fill ul li a {
  position: relative;
}
nav.stroke ul li a:after,
nav.fill ul li a:after {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
  margin-bottom: -0.8rem;
  width: 0%;
  content: '';
  color: transparent;
  background: rgb(235, 40, 40);
  height: 4px;
}
nav.stroke ul li a:hover:after {
  width: 100%;
}

    a {
        text-decoration: none;
    }
    a:hover {
        text-shadow: -1px 1px 2px black;
    }
    a:active {
        text-shadow: -1px 1px 0px black;
        transform: translateX(1px) translateY(1px);
    }
	/* :global([aria-current]) {
		border-bottom: 1px solid red;

	} */
	main {
		text-align: center;
		padding: 1em;
		max-width: 620px;
		margin: 0 auto;
		background: #979ee296;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
  }
main, nav {
  animation-name: animateappear;
  animation-duration: 1s;
  animation-fill-mode: both;
}
</style>