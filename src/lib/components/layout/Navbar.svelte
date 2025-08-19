<script lang="ts">
	import { Zap, Bird, Menu } from '@lucide/svelte';
	import { PUBLIC_APP_NAME } from '$env/static/public';
</script>

<div class="drawer">
	<!-- Drawer toggle -->
	<input id="navbar-drawer" type="checkbox" class="drawer-toggle" />

	<!-- Main Content -->
	<div class="drawer-content flex h-auto flex-col">
		<div id="top" class="navbar bg-base-100 flex justify-between px-3 shadow-md">
			<!-- Left section -->
			<div class="flex w-1/3 items-center justify-start">
				<div class="flex items-center gap-2">
					<a href="/" class="flex items-center gap-2">
						<div class="avatar border-secondary rounded-lg border p-2 2xl:hidden">
							<Bird />
						</div>
						<div class="avatar hidden rounded-lg 2xl:flex">
							<Zap />
						</div>
						<h2 class="hidden text-center text-sm font-semibold lg:flex">
							{PUBLIC_APP_NAME}
						</h2>
					</a>
				</div>
			</div>

			<!-- Center section -->
			<div class="flex w-1/3 items-center justify-center">
				<a href="/" class="text-center text-sm font-semibold lg:hidden">
					{PUBLIC_APP_NAME}
				</a>
				<!-- Desktop Navigation -->
				<div class="hidden lg:flex">
					<ul class="menu menu-horizontal">
						<li><a href="/auth">Sign In</a></li>
						<li><a href="/account">Account</a></li>
						<li><a href="#top">Privacy</a></li>
					</ul>
				</div>
			</div>

			<!-- Right section -->
			<div class="flex w-1/3 items-center justify-end gap-4">
				<a href="#top" class="btn btn-ghost btn-sm hidden lg:flex">Sign Up</a>

				<!-- Hamburger menu -->
				<div class="flex-none lg:hidden">
					<label for="navbar-drawer" class="btn btn-square btn-ghost">
						<Menu />
					</label>
				</div>
			</div>
		</div>
	</div>

	<!-- Sidebar -->
	<div class="drawer-side z-50">
		<label for="navbar-drawer" aria-label="close sidebar" class="drawer-overlay"></label>
		<aside class="bg-base-100 min-h-full w-64 border-r">
			<div class="bg-base-100 p-4">
				<div class="mb-6 flex items-center gap-3">
					<div class="avatar border-base-300 rounded-lg border p-2">
						<Bird />
					</div>
					<span class="text-md font-semibold">Menu</span>
				</div>
				<ul class="menu rounded-box bg-base-100 space-y-1">
					<li><a href="/auth">Sign In</a></li>
					<li><a href="/account">Account</a></li>
					<li><a href="#top">Contact</a></li>
					<li><a href="#top">Privacy</a></li>
				</ul>
			</div>
		</aside>
	</div>
</div>
