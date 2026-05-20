<script>
	const categories = [
		{ id: 'all', name: 'Semua' },
		{ id: 'pondok', name: 'Kegiatan Pondok' },
		{ id: 'formal', name: 'Pendidikan Formal' },
		{ id: 'ekstra', name: 'Ekstrakurikuler' }
	];

	const galleryItems = [
		{ id: 1, title: 'Wisuda Alfiyah Ibnu Malik', category: 'pondok', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974715_y-1.jpg', desc: 'Prosesi khataman bait Alfiyah Ibnu Malik oleh para santri senior.' },
		{ id: 2, title: 'Kajian Rutin Kitab Salaf', category: 'pondok', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974721_y.jpg', desc: 'Suasana khidmat pengajian kitab salaf oleh asatidzah pondok.' },
		{ id: 3, title: 'Upacara Peringatan Hari Besar', category: 'pondok', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974722_y.jpg', desc: 'Apel pagi dan peringatan Hari Santri Nasional di halaman pondok.' },
		{ id: 4, title: 'Ziarah Makam Wali', category: 'pondok', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974717_x.jpg', desc: 'Momen ziarah santri ke makam pendiri pondok pesantren dan awliya.' },
		{ id: 5, title: 'Laboratorium Komputer SMK', category: 'formal', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974723_x.jpg', desc: 'Praktikum siswa SMK Al Qodiriyah di laboratorium multimedia.' },
		{ id: 6, title: 'Gedung SMP Al Qodiriyah', category: 'formal', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974714_x.jpg', desc: 'Halaman depan gedung SMP Al Qodiriyah Windusari Magelang.' },
		{ id: 7, title: 'Hadrah Sunan Keling Al Qodiriyah', category: 'ekstra', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974718_x.jpg', desc: 'Penampilan tim majelis sholawat hadrah dalam acara resmi.' },
		{ id: 8, title: 'Pencak Silat PSHT Santri', category: 'ekstra', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974726_y-e1745139038743.jpg', desc: 'Latihan ketangkasan pencak silat PSHT untuk melatih fisik santri.' },
		{ id: 9, title: 'Khataman Al-Qur’an Juz Amma', category: 'pondok', image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6059745620098401215_y.jpg', desc: 'Khataman Al-Qur’an tingkat santri madrasah diniyah.' }
	];

	// Fix image path for SMK lab
	galleryItems[4].image = 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974723_x.jpg';

	let activeFilter = $state('all');
	let selectedItem = $state(null);

	const filteredItems = $derived(
		activeFilter === 'all' 
			? galleryItems 
			: galleryItems.filter(item => item.category === activeFilter)
	);

	function filterBy(categoryId) {
		activeFilter = categoryId;
	}

	function openLightbox(item) {
		selectedItem = item;
	}

	function closeLightbox() {
		selectedItem = null;
	}
</script>

<svelte:head>
	<title>Galeri Kegiatan – Ponpes Al Qodiriyah</title>
</svelte:head>

<!-- Header Banner -->
<section 
	class="relative py-24 bg-cover bg-center text-white" 
	style="background-image: linear-gradient(rgba(88, 70, 140, 0.8), rgba(70, 55, 112, 0.9)), url('https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974722_y.jpg');"
>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-4">
		<h1 class="text-4xl font-extrabold tracking-tight">Galeri Kegiatan</h1>
		<p class="text-purple-200 text-sm font-semibold max-w-xl mx-auto">
			Dokumentasi Foto Kegiatan Harian, Pembelajaran, dan Ekstrakurikuler Santri.
		</p>
	</div>
</section>

<!-- Gallery Grid & Filters -->
<section class="py-24 bg-white">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
		
		<!-- Filters -->
		<div class="flex flex-wrap justify-center gap-3">
			{#each categories as cat}
				<button 
					class="btn rounded-full font-bold px-6 border-none cursor-pointer transition-all duration-300
						{activeFilter === cat.id 
							? 'bg-brand-purple text-white shadow-md' 
							: 'bg-gray-100 text-gray-600 hover:bg-gray-200'}"
					onclick={() => filterBy(cat.id)}
				>
					{cat.name}
				</button>
			{/each}
		</div>

		<!-- Grid items -->
		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
			{#each filteredItems as item}
				<div 
					class="group card bg-white border border-gray-100 shadow-sm overflow-hidden hover:shadow-xl transition-all duration-300 cursor-pointer"
					onclick={() => openLightbox(item)}
					role="button"
					tabindex="0"
					onkeydown={(e) => e.key === 'Enter' && openLightbox(item)}
				>
					<figure class="relative h-64 overflow-hidden">
						<img 
							src={item.image} 
							alt={item.title} 
							class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" 
						/>
						<div class="absolute inset-0 bg-brand-purple/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
							<div class="w-12 h-12 bg-white rounded-full flex items-center justify-center text-brand-purple shadow-lg">
								<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
									<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
								</svg>
							</div>
						</div>
					</figure>
					<div class="card-body p-6">
						<span class="text-xs font-bold text-brand-teal uppercase tracking-wider">
							{categories.find(c => c.id === item.category)?.name}
						</span>
						<h3 class="card-title text-base font-bold text-brand-purple-dark group-hover:text-brand-purple transition-colors">
							{item.title}
						</h3>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Lightbox Modal -->
{#if selectedItem}
	<div 
		class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/85 backdrop-blur-sm transition-all"
		onclick={closeLightbox}
		role="button"
		tabindex="0"
		onkeydown={(e) => e.key === 'Escape' && closeLightbox()}
	>
		<div 
			class="relative max-w-4xl w-full bg-white rounded-3xl overflow-hidden shadow-2xl flex flex-col md:flex-row max-h-[90vh]"
			onclick={(e) => e.stopPropagation()}
			role="none"
		>
			<!-- Close button -->
			<button 
				class="absolute top-4 right-4 z-10 btn btn-circle btn-sm bg-black/50 hover:bg-black/80 text-white border-none cursor-pointer"
				onclick={closeLightbox}
			>
				✕
			</button>

			<!-- Photo side -->
			<div class="md:w-3/5 bg-black flex items-center justify-center min-h-[300px]">
				<img 
					src={selectedItem.image} 
					alt={selectedItem.title} 
					class="max-w-full max-h-[60vh] md:max-h-[80vh] object-contain"
				/>
			</div>

			<!-- Details side -->
			<div class="md:w-2/5 p-8 flex flex-col justify-between bg-white text-gray-800">
				<div class="space-y-4">
					<span class="badge bg-purple-50 text-brand-purple border-purple-100 font-semibold uppercase tracking-wider text-xs">
						{categories.find(c => c.id === selectedItem.category)?.name}
					</span>
					<h3 class="text-xl font-bold text-brand-purple-dark">{selectedItem.title}</h3>
					<p class="text-sm text-gray-500 leading-relaxed font-medium">
						{selectedItem.desc}
					</p>
				</div>

				<div class="pt-6 border-t border-gray-100 text-xs text-gray-400 font-medium">
					Ponpes Al Qodiriyah Hasan Ibrahim Windusari Magelang
				</div>
			</div>
		</div>
	</div>
{/if}
