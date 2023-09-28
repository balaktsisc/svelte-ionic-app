<script lang="ts">
	import { menu, code } from 'ionicons/icons';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { menuController } from 'ionic-svelte';
	import { IonPage } from 'ionic-svelte';
	import { register } from 'swiper/element/bundle';

	let menuIconClicked = false;

	const flipMenuOnOff = () => {
		setTimeout(() => {
			menuController.open('mainmenu');
			if (!menuIconClicked) {
				setTimeout(() => {
					menuController.close('mainmenu');
				}, 2000);
			}
		}, 2000);
	};

	const flipMenuOn = () => {
		menuIconClicked = true;
		menuController.open('mainmenu');
	};

	register();
</script>

<svelte:head>
	<title>ToDo for Dummies</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="end">
				<ion-menu-button/>
			</ion-buttons>
			<ion-title>Slides</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding" scroll-y={true}>
		<swiper-container pager={true} on:reachend={flipMenuOnOff}>
			<swiper-slide>
				<img src="/logo.svg" alt="pict" />
				<h2>Welcome!</h2>

				<b> Ionic UI App</b> is a demo of the ionic framework made with Svelte<br />


                <ion-card>
                    <ion-card-header>
                        <ion-card-subtitle>Card Subtitle</ion-card-subtitle>
                        <ion-card-title>Card Title</ion-card-title>
                    </ion-card-header>

                    <ion-card-content>
                        Keep close to Nature's heart... and break clear away, once in awhile, and climb a mountain
                        or spend a week in the woods. Wash your spirit clean.
                    </ion-card-content>
                </ion-card>

                <ion-card>
                    <ion-item>
                        <ion-icon slot="start" />

                        <ion-label>ion-item in a card, icon left, button right</ion-label>
                        <ion-button fill="outline" slot="end">View</ion-button>
                    </ion-item>

                    <ion-card-content>
                        This is content, without any paragraph or header tags, within an ion-card-content element.
                    </ion-card-content>
                </ion-card>

                <ion-card>
                    <ion-item href="/components/tabs/:tab" class="activated">
                        <ion-icon  slot="start" />
                        <ion-label>Card Link Item 1 .activated</ion-label>
                    </ion-item>

                    <ion-item href="/components/Button">
                        <ion-icon  slot="start" />
                        <ion-label>Card Link Item 2</ion-label>
                    </ion-item>

                    <ion-item class="activated">
                        <ion-icon  slot="start" />
                        <ion-label>Card Button Item 1 .activated</ion-label>
                    </ion-item>

                    <ion-item>
                        <ion-icon slot="start" />
                        <ion-label>Card Button Item 2</ion-label>
                    </ion-item>
                </ion-card>

                <ion-card>
                    <img src="/assets/img/madison.jpg" alt="madison" />
                    <ion-card-header>
                        <ion-card-subtitle>Destination</ion-card-subtitle>
                        <ion-card-title>Madison, WI</ion-card-title>
                    </ion-card-header>
                    <ion-card-content>
                        Founded in 1829 on an isthmus between Lake Monona and Lake Mendota, Madison was named the
                        capital of the Wisconsin Territory in 1836.
                    </ion-card-content>
                </ion-card>
            </swiper-slide>
		</swiper-container>
	</ion-content>
</IonPage>

<style>
	:root {
		--ion-safe-area-top: 20px;
		--ion-safe-area-bottom: 22px;
	}

	pre {
		font-size: 80%;
	}

	swiper-container {
		--swiper-pagination-bullet-inactive-color: var(--ion-color-step-200, #cccccc);
		--swiper-pagination-color: var(--ion-color-primary, #3880ff);
		--swiper-pagination-progressbar-bg-color: rgba(var(--ion-text-color-rgb, 0, 0, 0), 0.25);
		--swiper-scrollbar-bg-color: rgba(var(--ion-text-color-rgb, 0, 0, 0), 0.1);
		--swiper-scrollbar-drag-bg-color: rgba(var(--ion-text-color-rgb, 0, 0, 0), 0.5);
	}

	swiper-slide {
		display: flex;
		position: relative;
		flex-direction: column;

		flex-shrink: 0;
		align-items: center;
		justify-content: center;

		width: 100%;
		height: 100%;

		font-size: 18px;

		text-align: center;
		box-sizing: border-box;
	}

	swiper-slide img {
		width: auto;
		max-width: 40%;
		height: auto;
		max-height: 40%;
	}
</style>
