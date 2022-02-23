# 🚀 Astro headers

### [📘 Documentation →](https://astros.warps.it/documentation)

### [🧑‍🚀 Astro website →](https://astro.build/)


Collection of headers for astro.

You can find a live usage at [astros.warps.it](https://astros.warps.it/).

Headers included

| Name   | Description    |
| ------ | -------------- |
| Header | Default header |

## Header

### How To Use

```astro
---
...
/* Import the header you need */
import { Header } from "../index.js";
import routes from "../data/routes.json";

interface Props {
	pathname?: string;
}

const { pathname } = Astro.props as Props;
---

<html lang="en">
	<head>
	</head>
	<head>
		<body>
			<Header
				logo="your-logo.png"
				{pathname}
				navItems={routes}
				sticky={true}
				hideOnScroll={true}
			/>
			<main></main>
		</body>
	</head>
</html>
```

navItems should be an array of objects with the following properties:

```json
[
	{
		"title": "Home",
		"href": "/",
		"type": "link"
	},
	{
		"title": "Services",
		"href": "/services",
		"type": "link",
		"items": [
			{
				"title": "Service 1",
				"href": "/service1",
				"type": "link"
			},
			{
				"title": "Service 2",
				"href": "/service2",
				"type": "link"
			}
		]
	},
	{
		"title": "About",
		"href": "/about",
		"type": "link"
	},
	{
		"title": "Blog",
		"href": "/blog",
		"type": "link"
	},
	{
		"title": "Contacts",
		"href": "/contact",
		"type": "button"
	}
]
```

### Supported Props

| Propname             | Type      | Default   | Required | Description                                                              |
| -------------------- | --------- | --------- | -------- | ------------------------------------------------------------------------ |
| navItems             | NavItem[] | null      | X        | Items of the navbar (view above)                                         |
| pathname             | string    | null      | X        | Path of the current page, set with pathname={Astro.request.url.pathname} |
| sticky               | bool      | true      |          | Set the header as sticky (will follow throught the page)                 |
| blur                 | bool      | true      |          | Blur the header (for desktop only)                                       |
| hideOnScroll         | bool      | true      |          | Hide the header when scrolling down                                      |
| logo                 | string    | null      |          | Path of the logo image                                                   |
| showThemeSwitcher    | bool      | true      |          | Show the theme switcher                                                  |
| showLanguageSwitcher | bool      | true      |          | Show the language switcher                                               |
| hamburgerStyle       | string    | "minimal" |          | "Minimal" / "Fancy", layout for the hamburger style                      |
| lmap                 | string    | null      |          | Language map, required for localize labels on the header                 |
