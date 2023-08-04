<script setup>
	import { ref } from "vue"
	import { Menu, MenuButton, MenuItems, MenuItem, Dialog, DialogPanel, Disclosure, DisclosureButton, DisclosurePanel, Popover, PopoverButton, PopoverGroup, PopoverPanel } from "@headlessui/vue"
	import { ArrowPathIcon, Bars3Icon, ChartPieIcon, CursorArrowRaysIcon, FingerPrintIcon, SquaresPlusIcon, XMarkIcon } from "@heroicons/vue/24/outline"
	import { ChevronDownIcon, PhoneIcon, PlayCircleIcon } from "@heroicons/vue/20/solid"

	const products = [
		{ name: "Analytics", description: "Get a better understanding of your traffic", href: "#", icon: ChartPieIcon },
		{ name: "Engagement", description: "Speak directly to your customers", href: "#", icon: CursorArrowRaysIcon },
		{ name: "Security", description: "Your customers’ data will be safe and secure", href: "#", icon: FingerPrintIcon },
		{ name: "Integrations", description: "Connect with third-party tools", href: "#", icon: SquaresPlusIcon },
		{ name: "Automations", description: "Build strategic funnels that will convert", href: "#", icon: ArrowPathIcon },
	]
	const callsToAction = [
		{ name: "Watch demo", href: "#", icon: PlayCircleIcon },
		{ name: "Contact sales", href: "#", icon: PhoneIcon },
	]

	const mobileMenuOpen = ref(false)
</script>

<template>
	<header class="bg-white">
		<nav class="mx-auto flex max-w-7xl items-center justify-between" aria-label="Global">
			<div class="grow flex items-center">
				<a href="#" class="-m-1.5 p-1.5 text-xl font-semibold text-black hover:text-black mr-4"
					>Launch
					<!-- <span class="sr-only">Your Company</span>
					<img class="h-8 w-auto" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600" alt="" /> -->
				</a>
				<!-- <Popover class="relative">
					<PopoverButton class="flex items-center gap-x-1 text-sm font-semibold leading-6 text-gray-900">
						Product
						<ChevronDownIcon class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
					</PopoverButton>

					<transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0 translate-y-1" enter-to-class="opacity-100 translate-y-0" leave-active-class="transition ease-in duration-150" leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-1">
						<PopoverPanel class="absolute -left-8 top-full z-10 mt-3 w-screen max-w-md overflow-hidden rounded-3xl bg-white shadow-lg ring-1 ring-gray-900/5">
							<div class="p-4">
								<div v-for="item in products" :key="item.name" class="group relative flex items-center gap-x-6 rounded-lg p-4 text-sm leading-6 hover:bg-gray-50">
									<div class="flex h-11 w-11 flex-none items-center justify-center rounded-lg bg-gray-50 group-hover:bg-white">
										<component :is="item.icon" class="h-6 w-6 text-gray-600 group-hover:text-indigo-600" aria-hidden="true" />
									</div>
									<div class="flex-auto">
										<a :href="item.href" class="block font-semibold text-gray-900">
											{{ item.name }}
											<span class="absolute inset-0" />
										</a>
										<p class="mt-1 text-gray-600">{{ item.description }}</p>
									</div>
								</div>
							</div>
							<div class="grid grid-cols-2 divide-x divide-gray-900/5 bg-gray-50">
								<a v-for="item in callsToAction" :key="item.name" :href="item.href" class="flex items-center justify-center gap-x-2.5 p-3 text-sm font-semibold leading-6 text-gray-900 hover:bg-gray-100">
									<component :is="item.icon" class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
									{{ item.name }}
								</a>
							</div>
						</PopoverPanel>
					</transition>
				</Popover> -->
				<!-- dropdown -->
				<PopoverGroup class="hidden md:flex">
					<a href="#" class="text-sm text-black px-4 py-2">Home</a>

					<Menu as="div" class="relative inline-block text-left">
						<div>
							<MenuButton class="flex items-center gap-x-1 w-full bg-white px-4 py-2 text-sm font-semibold text-gray-600 border-0 focus:outline-none">
								Dropdown
								<ChevronDownIcon class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
							</MenuButton>
						</div>
						<transition
							enter-active-class="transition ease-out duration-100"
							enter-from-class="transform opacity-0 scale-95"
							enter-to-class="transform opacity-100 scale-100"
							leave-active-class="transition ease-in duration-75"
							leave-from-class="transform opacity-100 scale-100"
							leave-to-class="transform opacity-0 scale-95"
						>
							<MenuItems class="absolute left-0 z-10 mt-1 w-56 origin-top-left rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
								<div class="py-1">
									<a href="#" class="block px-4 py-2 text-sm text-gray-600">Account settings</a>
									<a href="#" class="block px-4 py-2 text-sm text-gray-600">Account settings</a>
									<a href="#" class="block px-4 py-2 text-sm text-gray-600">Account settings</a>

									<MenuItem v-slot="{ active }">
										<a href="#" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Support</a>
									</MenuItem>
									<form method="POST" action="#">
										<MenuItem v-slot="{ active }">
											<button type="submit" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block w-full px-4 py-2 text-left text-sm']">Sign out</button>
										</MenuItem>
									</form>
								</div>
							</MenuItems>
						</transition>
					</Menu>

					<a href="#" class="text-sm text-gray-600 px-4 py-2 hover:text-black transition-all duration-300">Feature</a>
					<a href="#" class="text-sm text-gray-600 px-4 py-2 hover:text-black transition-all duration-300">Price</a>
					<a href="#" class="text-sm text-gray-600 px-4 py-2 hover:text-black transition-all duration-300">About</a>
					<a href="#" class="text-sm text-gray-600 px-4 py-2 hover:text-black transition-all duration-300">Contact</a>
				</PopoverGroup>
				<!-- user / auth -->
				<div class="hidden lg:flex lg:flex-1 md:justify-end md:gap-x-1">
					<a href="#" class="shrink-0 border text-sm text-gray-600 rounded-full px-6 py-1.5 hover:border-black hover:text-black transition-all duration-300">Sign in</a>
					<a href="#" class="shrink-0 bg-blue-500 text-sm text-white rounded-full px-6 py-1.5">Register</a>
				</div>
			</div>
			<!-- open mobile sidebar -->
			<div class="flex md:hidden">
				<button type="button" class="inline-flex items-center justify-center rounded-md-m-0.5 text-gray-700 focus:outline-none border-0 p-1.5" @click="mobileMenuOpen = true">
					<Bars3Icon class="h-6 w-6" aria-hidden="true" />
				</button>
			</div>
		</nav>

		<Dialog as="div" class="md:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
			<div class="fixed inset-0 z-10" />
			<DialogPanel class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-white p-4 max-w-xs sm:max-w-sm ring-1 ring-gray-900/10">
				<div class="flex items-center justify-between">
					<a href="#" class="-m-1.5 p-1.5 text-xl font-semibold text-black hover:text-black mr-4"
						>Launch
						<!-- <img class="h-8 w-auto" src="https://tailwindui.com/img/logos/mark.svg?color=indigo&amp;shade=600" alt="" /> -->
					</a>
					<button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = false">
						<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
							<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"></path>
						</svg>
					</button>
				</div>
				<div class="mt-6">
					<div class="divide-y divide-gray-500/10">
						<div class="mb-3 space-y-1">
							<a href="#" class="block text-sm text-black py-2">Home</a>
							<a href="#" class="block text-sm text-gray-600 py-2 hover:text-black transition-all duration-300">Dropdown</a>
							<a href="#" class="block text-sm text-gray-600 py-2 hover:text-black transition-all duration-300">Feature</a>
							<a href="#" class="block text-sm text-gray-600 py-2 hover:text-black transition-all duration-300">Price</a>
							<a href="#" class="block text-sm text-gray-600 py-2 hover:text-black transition-all duration-300">Abotu</a>
							<a href="#" class="block text-sm text-gray-600 py-2 hover:text-black transition-all duration-300">Contact</a>
						</div>
						<div class="pt-6">
							<a href="#" class="border text-sm text-gray-600 rounded-full px-6 py-1.5 hover:border-black hover:text-black transition-all duration-300">Sign in</a>
							<a href="#" class="bg-blue-500 text-sm text-white rounded-full px-6 py-1.5">Register</a>
						</div>
					</div>
				</div>
			</DialogPanel>
		</Dialog>
	</header>
</template>
