<script>
	import { page } from '$app/state';
	import './layout.css';

	let { children } = $props();

	let isDrawerOpen = $state(false);

	const menuItems = [
		{ name: 'Beranda', path: '/' },
		{ 
			name: 'Halaman', 
			submenu: [
				{ name: 'Sekapur Sirih', path: '/sekapur-sirih' },
				{ name: 'Program Pesantren', path: '/program-pesantren' },
				{ name: 'Galeri', path: '/galeri-pesantren' }
			]
		},
		{ 
			name: 'Pendidikan Formal', 
			submenu: [
				{ name: 'SMK Al Qodiriyah', path: '/smk-alqodiriyah' },
				{ name: 'SMP Al Qodiriyah', path: '/smp-alqodiriyah' }
			]
		},
		{ name: 'Hubungi Kami', path: '/contact-us' }
	];

	function closeDrawer() {
		isDrawerOpen = false;
	}

	// Helper to check if a route is active
	function isActive(path, submenu) {
		const currentPath = page.url.pathname;
		if (submenu) {
			return submenu.some(sub => sub.path === currentPath);
		}
		if (path === '/') {
			return currentPath === '/';
		}
		return currentPath.startsWith(path);
	}
</script>

<svelte:head>
	<title>Ponpes Al Qodiriyah Hasan Ibrahim – Asrama Pendidikan Islam</title>
	<meta name="description" content="Pondok Pesantren Al Qodiriyah Windusari Magelang - Asrama Pendidikan Islam, SMK & SMP Al Qodiriyah." />
</svelte:head>

<div class="drawer drawer-end min-h-screen flex flex-col">
	<input id="my-drawer" type="checkbox" class="drawer-toggle" bind:checked={isDrawerOpen} />
	
	<div class="drawer-content flex flex-col flex-1">
		<!-- Navigation Header -->
		<header class="sticky top-0 z-50 bg-white/95 backdrop-blur-md shadow-sm border-b border-gray-100 transition-all duration-300">
			<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
				<div class="flex items-center justify-between h-20">
					<!-- Logo -->
					<a href="/" class="flex-shrink-0 flex items-center gap-3">
						<!-- Desktop / Tablet Logo (hidden on mobile, visible on sm and up) -->
						<img 
							src="https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/logo-ALQ-warna.png" 
							alt="Logo Ponpes Al Qodiriyah" 
							class="hidden sm:block h-12 w-auto object-contain" 
						/>
						
						<!-- Mobile Logo (visible on mobile, hidden on sm and up) -->
						<div class="flex sm:hidden items-center gap-2">
							<img 
								src="/favicon.png" 
								alt="Favicon Logo" 
								class="h-9 w-auto object-contain" 
							/>
							<span class="text-sm font-bold text-brand-purple">Al Qodiriyah</span>
						</div>
					</a>					<!-- Desktop Nav & CTA Group (Pushed to the right) -->
					<div class="hidden lg:flex items-center gap-10 ml-auto">
						<!-- Desktop Nav Items -->
						<nav class="flex items-center gap-8">
							{#each menuItems as item}
								{#if item.path === '/contact-us'}
									<!-- Skip rendering in desktop header main nav because it's rendered as the CTA button -->
								{:else if item.submenu}
									<div class="dropdown dropdown-hover dropdown-bottom dropdown-start">
										<button 
											tabindex="0"
											class="flex items-center gap-1.5 text-sm font-semibold transition-colors duration-200 py-2 cursor-pointer
												{isActive(null, item.submenu) ? 'text-brand-purple font-bold' : 'text-gray-600 hover:text-brand-purple'}"
										>
											{item.name}
											<svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 opacity-70" viewBox="0 0 20 20" fill="currentColor">
												<path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
											</svg>
										</button>
										<ul class="dropdown-content menu p-2 shadow-xl bg-white border border-gray-100 rounded-box w-52 z-30">
											{#each item.submenu as sub}
												<li>
													<a 
														href={sub.path} 
														class="py-2.5 px-4 text-sm font-medium hover:bg-purple-50 hover:text-brand-purple rounded-lg transition-colors
															{isActive(sub.path) ? 'text-brand-purple font-bold bg-purple-50/50' : 'text-gray-600'}"
													>
														{sub.name}
													</a>
												</li>
											{/each}
										</ul>
									</div>
								{:else}
									<a 
										href={item.path} 
										class="text-sm font-semibold transition-colors duration-200 py-2
											{isActive(item.path) ? 'text-brand-purple font-bold border-b-2 border-brand-purple' : 'text-gray-600 hover:text-brand-purple'}"
									>
										{item.name}
									</a>
								{/if}
							{/each}
						</nav>

						<!-- Action Buttons / CTA -->
						<div class="flex items-center gap-4">
							<a 
								href="/contact-us" 
								class="btn btn-primary bg-brand-purple hover:bg-brand-purple-dark text-white border-none font-semibold px-6 rounded-full transition-all duration-300 shadow-md hover:shadow-lg"
							>
								Hubungi Kami
							</a>
						</div>
					</div>

					<!-- Mobile Menu Button -->
					<div class="flex lg:hidden">
						<label for="my-drawer" class="btn btn-ghost btn-circle text-brand-purple drawer-button cursor-pointer">
							<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
							</svg>
						</label>
					</div>
				</div>
			</div>
		</header>

		<!-- Main Page Content -->
		<main class="flex-1">
			{@render children()}
		</main>

		<!-- Global Footer -->
		<footer class="bg-brand-purple-dark text-white pt-16 pb-8 mt-auto border-t border-purple-900/50">
			<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
				<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-16">
					<!-- Column 1: Info & About -->
					<div class="space-y-6">
						<!-- Desktop / Tablet Logo (hidden on mobile, visible on sm and up) -->
						<div class="hidden sm:block">
							<img 
								src="https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/logo-ALQ-putih-e1745130997505.png" 
								alt="Logo White" 
								class="h-12 w-auto object-contain" 
							/>
						</div>
						
						<!-- Mobile Logo and text (visible on mobile, hidden on sm and up) -->
						<div class="flex sm:hidden items-center gap-3">
							<img 
								src="/favicon.png" 
								alt="Favicon Logo" 
								class="h-9 w-auto object-contain" 
							/>
							<div>
								<span class="block text-sm font-bold tracking-wide">Ponpes Al Qodiriyah</span>
								<span class="block text-xs text-purple-200">Windusari, Magelang</span>
							</div>
						</div>
						<p class="text-sm text-purple-200 leading-relaxed">
							Asrama Pendidikan Islam, Pondok Pesantren Al Qodiriyah Windusari, didirikan sejak 2007 oleh Romo KH. Idris Syafe'i Marzuki.
						</p>
						<div class="pt-2">
							<a href="https://alqodiriyah.sch.id" target="_blank" rel="noopener noreferrer" class="text-brand-teal hover:underline text-sm font-semibold transition-all">
								Kunjungi Web Sekolah &rarr;
							</a>
						</div>
					</div>

					<!-- Column 2: Contact Info -->
					<div class="space-y-6">
						<h3 class="text-lg font-bold border-b border-purple-800 pb-3 tracking-wide">Hubungi Kami</h3>
						<ul class="space-y-3.5 text-sm text-purple-200">
							<li class="flex items-start gap-3">
								<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-brand-teal shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
									<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
									<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
								</svg>
								<a href="https://maps.app.goo.gl/Yag6tqbaKztezbgs9" target="_blank" rel="noopener noreferrer" class="hover:text-white hover:underline transition-colors">
									Bawang, Candisari, Windusari,<br />Magelang, Jawa Tengah
								</a>
							</li>
							<li class="flex items-center gap-3">
								<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-brand-teal shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
									<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
								</svg>
								<a href="mailto:ponpesalqodiriyah@gmail.com" class="hover:text-white transition-colors">
									ponpesalqodiriyah@gmail.com
								</a>
							</li>
							<li class="flex items-center gap-3">
								<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-brand-teal shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
									<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.94.725l.548 2.2a1 1 0 01-.321.988l-1.305.98a10.582 10.582 0 004.872 4.872l.98-1.305a1 1 0 01.988-.321l2.2.548a1 1 0 01.725.94V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
								</svg>
								<a href="tel:08123456789" class="hover:text-white transition-colors">
									08 123456789
								</a>
							</li>
						</ul>
					</div>

					<!-- Column 3: Quick Links -->
					<div class="space-y-6">
						<h3 class="text-lg font-bold border-b border-purple-800 pb-3 tracking-wide">Tautan Cepat</h3>
						<ul class="space-y-2.5 text-sm text-purple-200">
							<li><a href="/sekapur-sirih" class="hover:text-white hover:underline transition-colors">&bull; Sekapur Sirih (Profil)</a></li>
							<li><a href="/program-pesantren" class="hover:text-white hover:underline transition-colors">&bull; Program Pesantren</a></li>
							<li><a href="/galeri-pesantren" class="hover:text-white hover:underline transition-colors">&bull; Galeri Kegiatan</a></li>
							<li><a href="/smk-alqodiriyah" class="hover:text-white hover:underline transition-colors">&bull; SMK Al Qodiriyah</a></li>
							<li><a href="/smp-alqodiriyah" class="hover:text-white hover:underline transition-colors">&bull; SMP Al Qodiriyah</a></li>
						</ul>
					</div>

					<!-- Column 4: Mobile Portal Status -->
					<div class="space-y-6">
						<h3 class="text-lg font-bold border-b border-purple-800 pb-3 tracking-wide">Aplikasi Al Qodiriyah</h3>
						<div class="bg-purple-900/40 p-5 rounded-2xl border border-purple-800/80">
							<span class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-full text-xs font-semibold bg-brand-teal/20 text-brand-teal border border-brand-teal/20 mb-3">
								Dalam Pengembangan
							</span>
							<p class="text-xs text-purple-200 leading-relaxed mb-4">
								Aplikasi <strong>My Al Qodiriyah</strong>, portal satu pintu untuk santri, wali santri, dan umum. Nantikan peluncuran resminya!
							</p>
						</div>
					</div>
				</div>

				<!-- Copyright Footer -->
				<div class="border-t border-purple-900/60 pt-8 flex flex-col sm:flex-row items-center justify-between text-xs text-purple-300 gap-4">
					<p>&copy; {new Date().getFullYear()} Yayasan Al Qodiriyah Hasan Ibrahim. Hak Cipta Dilindungi.</p>
					<div class="flex items-center gap-6">
						<a href="https://www.youtube.com/@Ponpes_Al-Qodiriyah_Windusari" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">YouTube</a>
						<a href="https://www.instagram.com/ponpes_alqodiriyah/" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">Instagram</a>
						<a href="https://maps.app.goo.gl/Yag6tqbaKztezbgs9" target="_blank" rel="noopener noreferrer" class="hover:text-white transition-colors">Google Maps</a>
					</div>
				</div>
			</div>
		</footer>
	</div>

	<!-- Drawer Sidebar for Mobile -->
	<div class="drawer-side z-50">
		<label for="my-drawer" aria-label="close sidebar" class="drawer-overlay cursor-pointer"></label>
		<div class="menu p-6 w-80 min-h-full bg-white text-gray-800 flex flex-col gap-6 shadow-2xl">
			<!-- Header inside Sidebar -->
			<div class="flex items-center justify-between pb-4 border-b border-gray-100">
				<div class="flex items-center gap-2">
					<img src="/favicon.png" alt="Logo" class="h-10 w-auto object-contain" />
					<span class="text-sm font-bold text-brand-purple">Al Qodiriyah</span>
				</div>
				<button class="btn btn-ghost btn-sm btn-circle text-gray-400 hover:text-gray-600" onclick={closeDrawer} aria-label="Tutup Menu">
					<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
					</svg>
				</button>
			</div>

			<!-- Mobile Nav Menu links -->
			<ul class="menu p-0 flex-1 gap-2">
				{#each menuItems as item}
					{#if item.submenu}
						<li class="menu-title text-xs font-bold text-gray-400 uppercase tracking-wider mt-4">{item.name}</li>
						{#each item.submenu as sub}
							<li>
								<a 
									href={sub.path} 
									onclick={closeDrawer}
									class="py-3 px-4 font-semibold rounded-xl text-sm transition-all
										{isActive(sub.path) ? 'bg-purple-50 text-brand-purple font-bold' : 'text-gray-600 hover:bg-gray-50'}"
								>
									{sub.name}
								</a>
							</li>
						{/each}
					{:else}
						<li>
							<a 
								href={item.path} 
								onclick={closeDrawer}
								class="py-3 px-4 font-semibold rounded-xl text-sm transition-all mt-2
									{isActive(item.path) ? 'bg-purple-50 text-brand-purple font-bold' : 'text-gray-600 hover:bg-gray-50'}"
							>
								{item.name}
							</a>
						</li>
					{/if}
				{/each}
			</ul>

			<!-- CTA Button in mobile sidebar -->
			<div class="border-t border-gray-100 pt-6">
				<a 
					href="/contact-us" 
					onclick={closeDrawer}
					class="btn btn-primary bg-brand-purple hover:bg-brand-purple-dark text-white border-none w-full rounded-full font-bold"
				>
					Hubungi Kami
				</a>
			</div>
		</div>
	</div>
</div>
