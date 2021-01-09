<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png" />
		{{ this.feed }}
	</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
	name: "Home",

	data() {
		return {
			feed: null,
		};
	},

	components: {
		HelloWorld,
	},
	created() {
		let Parser = require("rss-parser");

		const CORS_PROXY = "https://cors-anywhere.herokuapp.com/";

		let parser = new Parser();
		parser.parseURL(
			CORS_PROXY + "http://feed43.com/4502845176441015.xml"
		).then((f) => {
      console.log(f.title);
				f.items.forEach(function(entry) {
          console.log(entry.title + ":" + entry.link);
				});
        this.feed = f;
    }).catch((error) => {
      console.log(error);
    });
	},
};
</script>
