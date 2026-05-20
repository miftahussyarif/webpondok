<script>
	import { onDestroy, onMount } from 'svelte';

	// Hero slides images and captions
	const slides = [
		{
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6059745620098401215_y.jpg',
			title: 'Teguh dalam Iman, Sholeh & Mandiri',
			subtitle: 'Membina generasi Rabbani yang berakhlakul karimah, berilmu luas, dan berkepribadian luhur.'
		},
		{
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974721_y.jpg',
			title: 'Asrama Pendidikan Islam Salaf & Modern',
			subtitle: 'Mengintegrasikan keilmuan kitab kuning klasik dengan penguasaan teknologi digital masa kini.'
		},
		{
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974722_y.jpg',
			title: 'Mencetak Santri Unggul & Berprestasi',
			subtitle: 'SMP & SMK Al Qodiriyah Windusari menyelenggarakan pendidikan formal berbasis pesantren.'
		}
	];

	let currentSlide = $state(0);
	let interval;

	onMount(() => {
		interval = setInterval(() => {
			currentSlide = (currentSlide + 1) % slides.length;
		}, 6000);
	});

	onDestroy(() => {
		if (interval) clearInterval(interval);
	});

	function setSlide(index) {
		currentSlide = index;
	}

	const subInstitutions = [
		{
			title: 'Pondok Pesantren Al Qodiriyah',
			desc: "Asrama Pendidikan Islam, Pondok Pesantren Al Qodiriyah Windusari, didirikan sejak 2007 oleh Romo KH. Idris Syafe'i Marzuki.",
			link: 'https://alqodiriyah.sch.id/',
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974717_x.jpg',
			tag: 'Salafiyah'
		},
		{
			title: 'SMK Al Qodiriyah Windusari',
			desc: 'SMK Al Qodiriyah Windusari membuka jurusan Multimedia sebagai acuan perkembangan dunia digital untuk santri.',
			link: 'https://alqodiriyah.sch.id/',
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974723_x.jpg',
			tag: 'Multimedia'
		},
		{
			title: 'SMP Al Qodiriyah Windusari',
			desc: 'SMP Al Qodiriyah, sebagai wadah Pendidikan menengah dibawah naungan Yayasan Al Qodiriyah Hasan Ibrahim Magelang.',
			link: 'https://alqodiriyah.sch.id/',
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974714_x.jpg',
			tag: 'Pendidikan Menengah'
		}
	];

	const curricula = [
		{
			title: 'Nahwu - Shorof',
			desc: 'Pembelajaran dasar bagi para santri, untuk mendalami berbagai kitab kuning salaf.',
			icon: '📖'
		},
		{
			title: 'Hadist - Tafsir',
			desc: "Dimulai dari Arbain Nawawi, sampai dengan Shahih Bukhari beserta matan-nya.",
			icon: '🕌'
		},
		{
			title: 'Fiqih',
			desc: 'Sebagai dasar pengamalan syariat, dari Fathul Qarib sampai dengan Fathul Wahhab.',
			icon: '⚖️'
		},
		{
			title: 'Tauhid & Tasawuf',
			desc: "Pembelajaran Ihya' Ulumuddin dan sebagainya, sebagai pelengkap tauhid dan penyeimbang akhlak.",
			icon: '💎'
		}
	];

	const programs = [
		{
			title: 'Seni Hadrah',
			desc: 'Extrakurikuler Seni Hadrah dan Sholawat, Majelis Sholawat Al Qodiriyah Hasan Ibrahim.',
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974718_x.jpg',
			tag: 'Hadrah'
		},
		{
			title: 'Pencak Silat PSHT',
			desc: 'Extrakurikuler Seni Pencak Silat PSHT sebagai sarana memupuk kebugaran dan ketangkasan santri.',
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974726_y-e1745139038743.jpg',
			tag: 'Silat'
		},
		{
			title: 'Program Tahfidz',
			desc: 'Program Tahfidzul Qur’an untuk santri salaf yang telah menempuh kurikulum dasar pesantren.',
			image: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6059745620098401215_y.jpg',
			tag: 'Tahfidz'
		}
	];
</script>

<!-- Hero Section with Slideshow -->
<section class="relative h-[85vh] w-full overflow-hidden bg-gray-900 text-white">
	{#each slides as slide, i}
		<div 
			class="absolute inset-0 w-full h-full bg-cover bg-center transition-opacity duration-1000 ease-in-out"
			style="background-image: linear-gradient(rgba(40, 20, 90, 0.45), rgba(20, 10, 50, 0.75)), url({slide.image}); opacity: {currentSlide === i ? 1 : 0}; z-index: {currentSlide === i ? 1 : 0};"
		>
			<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-full flex flex-col justify-center items-start">
				<div class="max-w-3xl space-y-6 transform translate-y-0 transition-transform duration-700">
					<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-semibold bg-brand-teal text-white border border-brand-teal/30 tracking-wide uppercase">
						Pondok Pesantren Al Qodiriyah
					</span>
					<h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight leading-tight drop-shadow-sm font-sans">
						{slide.title}
					</h1>
					<p class="text-lg sm:text-xl text-purple-100 leading-relaxed font-medium max-w-2xl drop-shadow-sm">
						{slide.subtitle}
					</p>
					<div class="flex flex-wrap gap-4 pt-4">
						<a 
							href="https://alqodiriyah.sch.id/ppdb2026/" 
							class="btn btn-primary bg-brand-teal hover:bg-brand-teal/90 text-brand-purple-dark border-none font-bold rounded-full px-8 py-3.5 shadow-lg hover:shadow-brand-teal/20 transition-all duration-300"
						>
							Pendaftaran Santri
						</a>
						<a 
							href="/sekapur-sirih" 
							class="btn btn-outline border-white hover:bg-white hover:text-brand-purple-dark font-bold rounded-full px-8 py-3.5 transition-all duration-300"
						>
							Profil Pesantren
						</a>
					</div>
				</div>
			</div>
		</div>
	{/each}

	<!-- Slider Controls Indicators -->
	<div class="absolute bottom-8 left-0 right-0 z-20 flex justify-center gap-3">
		{#each slides as _, i}
			<button 
				aria-label="Slide {i + 1}"
				class="w-10 h-1.5 rounded-full transition-all duration-300 cursor-pointer
					{currentSlide === i ? 'bg-brand-teal w-12' : 'bg-white/40 hover:bg-white/60'}"
				onclick={() => setSlide(i)}
			></button>
		{/each}
	</div>
</section>

<!-- Cards Section (Three Pillars) -->
<section class="relative z-10 -mt-20 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
	<div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
		{#each subInstitutions as inst}
			<div class="card bg-white shadow-xl hover:shadow-2xl hover:-translate-y-2 transition-all duration-300 border border-gray-100 overflow-hidden flex flex-col justify-between">
				<div>
					<figure class="relative h-56 w-full overflow-hidden">
						<img src={inst.image} alt={inst.title} class="w-full h-full object-cover" />
						<div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"></div>
						<span class="absolute top-4 left-4 badge bg-brand-purple text-white border-none font-semibold px-3 py-2 text-xs">
							{inst.tag}
						</span>
					</figure>
					<div class="card-body p-8 space-y-3">
						<h3 class="card-title text-xl font-bold text-brand-purple-dark leading-snug">
							{inst.title}
						</h3>
						<p class="text-sm text-gray-600 leading-relaxed font-medium">
							{inst.desc}
						</p>
					</div>
				</div>
				<div class="p-8 pt-0">
					<a 
						href={inst.link} 
						target="_blank" 
						rel="noopener noreferrer" 
						class="btn btn-outline border-brand-purple text-brand-purple hover:bg-brand-purple hover:text-white font-bold w-full rounded-xl transition-all duration-300"
					>
						Selengkapnya
					</a>
				</div>
			</div>
		{/each}
	</div>
</section>

<!-- Introduction Profile Summary Section -->
<section class="py-24 bg-white">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
			<div class="lg:col-span-6 space-y-6">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Profil Singkat
				</span>
				<h2 class="text-3xl sm:text-4xl font-extrabold text-brand-purple-dark tracking-tight leading-tight font-sans">
					Ngaji + Sekolah?<br class="hidden sm:inline" /> Al-Qodiriyah Aja!
				</h2>
				<p class="text-base text-gray-600 leading-relaxed font-medium">
					Pondok Pesantren Al Qodiriyah didirikan pada tahun 2005 oleh KH. Muhammad Idris Syafe'i Marzuki. Yayasan Al Qodiriyah Hasan Ibrahim berkomitmen menyelenggarakan asrama pendidikan Islam salafiyah klasik berpadu selaras dengan sekolah formal unggul terakreditasi baik tingkat SMP maupun SMK.
				</p>
				<div class="pt-4 flex flex-wrap gap-4">
					<a href="/sekapur-sirih" class="btn bg-brand-purple hover:bg-brand-purple-dark text-white border-none font-bold rounded-xl px-6 py-3 transition-colors">
						Profil Lengkap
					</a>
					<a href="/contact-us" class="btn btn-ghost text-brand-purple font-bold px-6">
						Hubungi Pengurus &rarr;
					</a>
				</div>
			</div>
			<div class="lg:col-span-6">
				<div class="relative">
					<div class="absolute -top-4 -left-4 w-72 h-72 bg-purple-100 rounded-3xl -z-10 transform -rotate-6"></div>
					<div class="absolute -bottom-4 -right-4 w-72 h-72 bg-blue-100 rounded-3xl -z-10 transform rotate-6"></div>
					<img 
						src="https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974715_y-1.jpg" 
						alt="Santri Al Qodiriyah" 
						class="w-full h-auto rounded-3xl object-cover shadow-2xl border-4 border-white"
					/>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Curriculum Section -->
<section class="py-24 bg-gradient-to-b from-[#fcfbfe] to-purple-50/50">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="text-center max-w-3xl mx-auto space-y-4 mb-16">
			<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
				Kurikulum Salafiyah
			</span>
			<h2 class="text-3xl sm:text-4xl font-extrabold text-brand-purple-dark tracking-tight">
				Mendalami Khazanah Kitab Kuning
			</h2>
			<p class="text-base text-gray-500 font-medium">
				Kurikulum kepesantrenan di Al Qodiriyah disusun secara sistematis mulai dari dasar pemahaman gramatika Arab hingga kajian hadits dan fiqih tematik.
			</p>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
			{#each curricula as cur}
				<div class="bg-white p-8 rounded-2xl shadow-md border border-purple-100/50 hover:shadow-xl hover:-translate-y-1.5 transition-all duration-300 space-y-4">
					<div class="w-14 h-14 rounded-2xl bg-purple-50 flex items-center justify-center text-3xl shadow-inner">
						{cur.icon}
					</div>
					<h3 class="text-lg font-extrabold text-brand-purple-dark">{cur.title}</h3>
					<p class="text-sm text-gray-600 leading-relaxed font-medium">{cur.desc}</p>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Featured Extracurricular Section -->
<section class="py-24 bg-white">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="text-center max-w-3xl mx-auto space-y-4 mb-16">
			<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
				Ekstrakurikuler
			</span>
			<h2 class="text-3xl sm:text-4xl font-extrabold text-brand-purple-dark tracking-tight">
				Program Unggulan Santri
			</h2>
			<p class="text-base text-gray-500 font-medium">
				Kami mendukung minat, bakat, kebugaran jasmani, dan keterampilan seni budaya islami santri melalui program ekstrakurikuler terstruktur.
			</p>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
			{#each programs as prog}
				<div class="group relative rounded-3xl overflow-hidden shadow-lg h-96 transition-all duration-500">
					<img src={prog.image} alt={prog.title} class="absolute inset-0 w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" />
					<div class="absolute inset-0 bg-gradient-to-t from-brand-purple-dark/95 via-brand-purple-dark/50 to-transparent"></div>
					<div class="absolute inset-x-0 bottom-0 p-8 space-y-3.5 text-white">
						<span class="inline-block px-2.5 py-1 rounded-lg text-xs font-semibold bg-brand-teal text-brand-purple-dark uppercase tracking-wide">
							{prog.tag}
						</span>
						<h3 class="text-xl font-bold tracking-tight">{prog.title}</h3>
						<p class="text-xs text-purple-100 leading-relaxed font-medium opacity-0 group-hover:opacity-100 transition-opacity duration-500">
							{prog.desc}
						</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Social Banners Section (YouTube, WhatsApp, Instagram) -->
<section class="py-20 bg-brand-purple-dark text-white relative overflow-hidden">
	<!-- Background subtle details -->
	<div class="absolute -top-32 -left-32 w-96 h-96 bg-brand-purple rounded-full opacity-20 filter blur-3xl"></div>
	<div class="absolute -bottom-32 -right-32 w-96 h-96 bg-brand-teal rounded-full opacity-10 filter blur-3xl"></div>

	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
		<div class="text-center max-w-2xl mx-auto space-y-4 mb-16">
			<h2 class="text-3xl font-extrabold tracking-tight">Lebih Dekat Bersama Kami</h2>
			<p class="text-sm text-purple-200 font-medium">Ikuti berita, siaran pengajian, jepretan foto, dan tanyakan langsung ke pengurus asrama.</p>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
			<!-- Youtube Card -->
			<a 
				href="https://www.youtube.com/@Ponpes_Al-Qodiriyah_Windusari" 
				target="_blank" 
				rel="noopener noreferrer" 
				class="bg-purple-900/30 border border-purple-800 p-8 rounded-3xl hover:bg-red-600/10 hover:border-red-500/50 hover:-translate-y-1.5 transition-all duration-300 flex flex-col justify-between h-56"
			>
				<div class="space-y-4">
					<div class="w-12 h-12 bg-red-600 rounded-2xl flex items-center justify-center text-white shadow-md">
						<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 fill-current" viewBox="0 0 24 24">
							<path d="M23.498 6.163a3.003 3.003 0 0 0-2.11-2.107C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.388.511a3.002 3.002 0 0 0-2.11 2.107C0 8.053 0 12 0 12s0 3.947.502 5.837a3.003 3.003 0 0 0 2.11 2.107C4.495 20.455 12 20.455 12 20.455s7.505 0 9.388-.511a3.002 3.002 0 0 0 2.11-2.107C24 15.947 24 12 24 12s0-3.947-.502-5.837zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
						</svg>
					</div>
					<div>
						<h3 class="text-lg font-bold">YouTube Official</h3>
						<p class="text-xs text-purple-200 mt-1">Video kegiatan, ceramah, sholawat, dan dokumenter pesantren.</p>
					</div>
				</div>
				<span class="text-xs font-semibold text-purple-300 group-hover:text-white flex items-center gap-1 mt-2">
					Tonton Sekarang &rarr;
				</span>
			</a>

			<!-- WA Card -->
			<a 
				href="https://wa.me/628123456789" 
				target="_blank" 
				rel="noopener noreferrer" 
				class="bg-purple-900/30 border border-purple-800 p-8 rounded-3xl hover:bg-emerald-600/10 hover:border-emerald-500/50 hover:-translate-y-1.5 transition-all duration-300 flex flex-col justify-between h-56"
			>
				<div class="space-y-4">
					<div class="w-12 h-12 bg-emerald-600 rounded-2xl flex items-center justify-center text-white shadow-md">
						<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 fill-current" viewBox="0 0 24 24">
							<path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946C.06 5.348 5.397.01 12.008.01c3.202.001 6.212 1.246 8.477 3.514 2.266 2.268 3.507 5.28 3.505 8.484-.004 6.657-5.34 11.997-11.953 11.997-2.005-.001-3.973-.502-5.724-1.455L0 24zm5.735-3.305c1.552.921 3.09 1.403 4.86 1.404 5.367 0 9.733-4.344 9.736-9.684.001-2.586-1.002-5.018-2.825-6.842S13.25 2.76 10.662 2.76c-5.372 0-9.742 4.346-9.745 9.687-.001 1.885.509 3.398 1.488 4.921L1.396 21.05l3.856-1.012h.54zm12.52-5.405c-.328-.164-1.942-.959-2.242-1.069-.3-.109-.519-.164-.738.164-.219.328-.849 1.069-1.04 1.288-.192.219-.383.246-.711.082-.328-.164-1.386-.511-2.64-1.631-.975-.87-1.633-1.946-1.825-2.274-.192-.328-.02-.505.144-.668.148-.146.328-.383.493-.575.164-.192.219-.328.328-.547.11-.219.055-.411-.027-.575-.082-.164-.738-1.78-.984-2.383-.247-.604-.519-.503-.738-.514-.191-.008-.41-.01-.629-.01-.219 0-.575.082-.876.411-.3.328-1.148 1.123-1.148 2.739 0 1.616 1.176 3.178 1.34 3.397.164.219 2.315 3.535 5.607 4.953.783.337 1.395.54 1.872.692.787.25 1.5.215 2.066.13.63-.094 1.942-.794 2.216-1.56.274-.767.274-1.423.192-1.56-.083-.137-.274-.219-.602-.383z"/>
						</svg>
					</div>
					<div>
						<h3 class="text-lg font-bold">Pengurus WhatsApp</h3>
						<p class="text-xs text-purple-200 mt-1">Layanan komunikasi langsung dengan sekretariat pondok.</p>
					</div>
				</div>
				<span class="text-xs font-semibold text-purple-300 group-hover:text-white flex items-center gap-1 mt-2">
					Hubungi Sekarang &rarr;
				</span>
			</a>

			<!-- Instagram Card -->
			<a 
				href="https://www.instagram.com/ponpes_alqodiriyah/" 
				target="_blank" 
				rel="noopener noreferrer" 
				class="bg-purple-900/30 border border-purple-800 p-8 rounded-3xl hover:bg-pink-600/10 hover:border-pink-500/50 hover:-translate-y-1.5 transition-all duration-300 flex flex-col justify-between h-56"
			>
				<div class="space-y-4">
					<div class="w-12 h-12 bg-pink-600 rounded-2xl flex items-center justify-center text-white shadow-md">
						<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 fill-current" viewBox="0 0 24 24">
							<path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.051.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/>
						</svg>
					</div>
					<div>
						<h3 class="text-lg font-bold">Instagram NEWS Feed</h3>
						<p class="text-xs text-purple-200 mt-1">Foto dokumentasi aktivitas harian dan kutipan ilmu bermanfaat.</p>
					</div>
				</div>
				<span class="text-xs font-semibold text-purple-300 group-hover:text-white flex items-center gap-1 mt-2">
					Lihat Galeri &rarr;
				</span>
			</a>
		</div>
	</div>
</section>

<!-- Call to Action Banner (Join Us) -->
<section class="py-24 bg-white relative overflow-hidden">
	<div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center relative z-10 space-y-8">
		<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-amber-50 text-amber-700 border border-amber-200 uppercase tracking-wide">
			Penerimaan Santri Baru
		</span>
		<h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-brand-purple-dark leading-tight tracking-tight max-w-4xl mx-auto">
			Penerimaan Santri & Siswa Baru Tahun Ajaran 2025/2026 Telah Dibuka!
		</h2>
		<p class="text-base text-gray-500 font-semibold max-w-2xl mx-auto">
			Jangan lewatkan kesempatan menjadi bagian dari asrama pendidikan Al Qodiriyah Hasan Ibrahim. Kuota pendaftaran terbatas untuk masing-masing jenjang.
		</p>
		<div class="flex flex-wrap justify-center gap-5 pt-4">
			<a 
				href="https://alqodiriyah.sch.id/ppdb2026" 
				class="btn btn-primary bg-brand-purple hover:bg-brand-purple-dark text-white border-none font-bold rounded-xl px-8 py-3.5 shadow-lg shadow-purple-900/10 transition-all duration-300"
			>
				Daftar Sekarang
			</a>
			<a 
				href="https://alqodiriyah.sch.id/ppdb2026" 
				class="btn btn-outline border-purple-200 text-brand-purple-light hover:bg-purple-50 font-bold rounded-xl px-8 py-3.5 transition-all duration-300"
			>
				Download Brosur (PDF)
			</a>
		</div>
	</div>
</section>
