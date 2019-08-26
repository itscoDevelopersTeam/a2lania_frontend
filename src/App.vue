<template>
	<v-app>
		<!-- Barra de navegación -->
		<v-navigation-drawer app>
			<v-list-item>
				<v-list-item-content>
					<v-list-item-title class="title">
						Application
					</v-list-item-title>
					<v-list-item-subtitle>
						subtext
					</v-list-item-subtitle>
				</v-list-item-content>
			</v-list-item>
	
			<v-divider></v-divider>
	
			<v-list dense nav>
				<v-list-item v-for="item in items" :key="item.title" link>
					<v-list-item-icon>
						<v-icon>{{ item.icon }}</v-icon>
					</v-list-item-icon>
		
					<v-list-item :to="item.route">
						<v-list-item-title>{{ item.title }}</v-list-item-title>
					</v-list-item>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>

		<!-- Barra de título -->
		<v-app-bar app>
			<v-toolbar-title class="headline text-uppercase">
				<span>A2LANIA</span>
				<span class="font-weight-light">Home</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn
				text
				href="https://github.com/vuetifyjs/vuetify/releases/latest"
				target="_blank"
			>
				<span class="mr-2">Latest Release</span>
				<v-icon>mdi-open-in-new</v-icon>
			</v-btn>
		</v-app-bar>

		<v-content>
			<router-view/>
		</v-content>
	</v-app>
</template>

<script>

export default {
	name: 'App',
	data() {
		return {
			items: [
				{ title: 'Cursos', icon: 'mdi-view-dashboard', route: 'cursos' },
				{ title: 'Reportes', icon: 'mdi-file-chart', route: 'reportes' },
				{ title: 'Cierre', icon: 'mdi-close-circle', route: 'cierre' },
				{ title: 'Diplomas', icon: 'mdi-newspaper-variant-outline', route: 'diplomas' },
				{ title: 'Calendario', icon: 'mdi-calendar', route: 'calendario' },
        	],
        	right: null,
		}
	},
};
</script>
