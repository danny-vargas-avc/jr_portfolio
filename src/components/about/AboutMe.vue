<script>
import ContactDetails from '@/components/contact/ContactDetails.vue';

export default {
	components: {
		ContactDetails,
	},
	data: () => {
		return {
			contacts: [
				{
					id: 1,
					name: 'Huntington Beach, CA',
					icon: 'map-pin',
				},
				{
					id: 2,
					name: 'evargasarch@gmail.com',
					icon: 'mail',
				},
				{
					id: 3,
					name: '(714) 752-9761',
					icon: 'phone',
				},
			],
		};
	},
	setup() {
		return {
			bios: [
				{
					id: 1,
					bio:
						'Architectural Designer with 4+ years of work experience in Architectural Services.',
				},
				{
					id: 2,
					bio:
						'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nihil vel illum asperiores dignissimos cumque quibusdam et fugiat voluptatem nobis suscipit explicabo, eaque consequatur nesciunt, fugit eligendi corporis laudantium adipisci soluta?',
				},
			],
		};
	},
};
</script>

<template>
	<div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
		<!-- About profile image -->
		<div class="w-full sm:w-1/4 mb-7 sm:mb-0">
			<img
				src="@/assets/images/jr_profile_image.jpeg"
				class="rounded-xl w-96"
				alt=""
			/>
		</div>

		<!-- About details -->
		<div class="w-full sm:w-3/4 text-left">
			<p
				v-for="bio in bios"
				:key="bio.id"
				class="font-general-regular mb-4 text-ternary-dark dark:text-ternary-light text-lg"
			>
				{{ bio.bio }}
			</p>
			<!-- Contact details -->
			<ContactDetails :contacts="contacts" />
		</div>
	</div>
</template>
