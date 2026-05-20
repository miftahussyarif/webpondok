<script>
	const innovations = [
		{ icon: '🎨', title: 'Desain Grafis & Fotografi', desc: 'Santri dilatih menguasai Adobe Photoshop, Illustrator, dan teknik fotografi digital untuk kebutuhan konten kreatif profesional.' },
		{ icon: '🎬', title: 'Perfilman & Videografi', desc: 'Produksi film pendek, dokumenter, dan iklan video dengan teknik sinematografi dan editing non-linear menggunakan Premiere Pro.' },
		{ icon: '🌐', title: 'Web Design & Digital Marketing', desc: 'Perancangan website responsif dan strategi pemasaran digital termasuk SEO, media sosial, dan konten marketing.' }
	];

	const achievements = [
		{ icon: '🏆', label: 'Akreditasi B', sub: 'BAN-S/M Kemdikbud RI' },
		{ icon: '📚', label: 'Jurusan Multimedia', sub: 'Kompetensi Keahlian Resmi' },
		{ icon: '🕌', label: 'Berbasis Pesantren', sub: 'Yayasan Al Qodiriyah' },
		{ icon: '📍', label: 'NPSN 69949720', sub: 'Terdata Kemendikbud' }
	];

	const photos = [
		{ src: 'https://image.alqodiriyah.sch.id/uploads/2022/01/unbk.jpg', alt: 'Ujian Berbasis Komputer (UNBK) SMK Al Qodiriyah', caption: 'Pelaksanaan UNBK' },
		{ src: 'https://image.alqodiriyah.sch.id/uploads/2022/01/paskib.jpg', alt: 'Paskibra SMK Al Qodiriyah Windusari', caption: 'Ekstrakurikuler Paskibra' },
		{ src: 'https://image.alqodiriyah.sch.id/uploads/2022/01/UPACARA.png', alt: 'Upacara Bendera SMK Al Qodiriyah', caption: 'Upacara Bendera' }
	];
</script>

<svelte:head>
	<title>SMK Al Qodiriyah Windusari Magelang – Jurusan Multimedia Berbasis Pesantren</title>
	<meta name="description" content="SMK Al Qodiriyah Windusari Magelang adalah sekolah menengah kejuruan swasta berakreditasi B di bawah Yayasan Al Qodiriyah Hasan Ibrahim. Membuka jurusan Multimedia meliputi desain grafis, fotografi, perfilman, dan web design." />
	<meta name="keywords" content="SMK Al Qodiriyah, Windusari Magelang, SMK Multimedia Magelang, sekolah vokasi pesantren, SMKS Al Qodiriyah" />
</svelte:head>

<!-- Header Banner -->
<section 
	class="relative py-28 bg-cover bg-center text-white" 
	style="background-image: linear-gradient(rgba(88, 70, 140, 0.85), rgba(70, 55, 112, 0.92)), url('https://image.alqodiriyah.sch.id/uploads/2022/01/UPACARA.png');"
>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-5">
		<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-white/20 text-white border border-white/30 uppercase tracking-wide">
			Pendidikan Menengah Kejuruan
		</span>
		<h1 class="text-4xl sm:text-5xl font-extrabold tracking-tight">SMK Al Qodiriyah</h1>
		<p class="text-purple-200 text-base font-semibold max-w-2xl mx-auto leading-relaxed">
			Sekolah Menengah Kejuruan Swasta Berbasis Pesantren dengan Kompetensi Keahlian Multimedia di Windusari, Magelang.
		</p>
	</div>
</section>

<!-- Stats / Achievements Bar -->
<section class="bg-brand-purple py-8 border-b border-purple-900/30">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="grid grid-cols-2 md:grid-cols-4 gap-6 text-white text-center">
			{#each achievements as ach}
				<div class="space-y-1">
					<div class="text-2xl">{ach.icon}</div>
					<div class="font-extrabold text-sm tracking-wide">{ach.label}</div>
					<div class="text-purple-200 text-xs font-medium">{ach.sub}</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Main Details -->
<section class="py-24 bg-white">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-24">
		
		<!-- Overview Row -->
		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
			<div class="lg:col-span-7 space-y-6">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Vokasi Digital
				</span>
				<h2 class="text-3xl font-extrabold text-brand-purple-dark tracking-tight">
					SMK Al Qodiriyah Windusari Magelang
				</h2>
				<p class="text-base text-gray-600 leading-relaxed font-medium">
					SMKS Al Qodiriyah Windusari adalah sekolah menengah kejuruan swasta yang beralamat di Jl. Lettu Sobandi Km.02, Dusun Bawang, Desa Candisari, Kecamatan Windusari, Kabupaten Magelang, Jawa Tengah. Sekolah ini berada di bawah naungan <strong>Yayasan Al Qodiriyah Hasan Ibrahim</strong>, yang juga mengelola Pondok Pesantren Al Qodiriyah.
				</p>
				<p class="text-base text-gray-600 leading-relaxed font-medium">
					Dengan Kompetensi Keahlian <strong>Multimedia</strong>, SMK Al Qodiriyah memadukan pendidikan vokasi modern dengan nilai-nilai kepesantrenan, menghasilkan lulusan yang kompeten secara teknis sekaligus berakhlak mulia.
				</p>
				<div class="flex flex-wrap gap-4 pt-2">
					<a href="https://alqodiriyah.sch.id/" target="_blank" rel="noopener noreferrer" class="btn bg-brand-purple hover:bg-brand-purple-dark text-white border-none font-bold rounded-xl px-6">
						Kunjungi Web Sekolah
					</a>
					<a href="https://maps.app.goo.gl/Yag6tqbaKztezbgs9" target="_blank" rel="noopener noreferrer" class="btn btn-outline border-purple-200 text-brand-purple hover:bg-purple-50 font-bold rounded-xl px-6">
						Petunjuk Lokasi Maps
					</a>
				</div>
			</div>
			
			<div class="lg:col-span-5">
				<img 
					src="https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974723_x.jpg" 
					alt="Laboratorium Multimedia SMK Al Qodiriyah Windusari Magelang" 
					class="w-full h-80 object-cover rounded-3xl shadow-xl border border-gray-100"
				/>
			</div>
		</div>

		<hr class="border-gray-100" />

		<!-- Photo Gallery Row -->
		<div class="space-y-10">
			<div class="text-center max-w-2xl mx-auto space-y-3">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Dokumentasi Kegiatan
				</span>
				<h2 class="text-3xl font-extrabold text-brand-purple-dark">Potret Kegiatan SMK Al Qodiriyah</h2>
				<p class="text-sm text-gray-400 font-medium">Berbagai kegiatan akademik dan non-akademik siswa SMK Al Qodiriyah Windusari.</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-3 gap-6">
				{#each photos as photo}
					<div class="group relative overflow-hidden rounded-3xl shadow-md border border-gray-100 hover:shadow-xl transition-all duration-300">
						<img
							src={photo.src}
							alt={photo.alt}
							class="w-full h-60 object-cover group-hover:scale-105 transition-transform duration-500"
						/>
						<div class="absolute inset-0 bg-gradient-to-t from-brand-purple/80 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-5">
							<span class="text-white text-sm font-bold">{photo.caption}</span>
						</div>
					</div>
				{/each}
			</div>
		</div>

		<hr class="border-gray-100" />

		<!-- Innovations Grid -->
		<div class="space-y-12">
			<div class="text-center max-w-2xl mx-auto space-y-3">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Kompetensi Keahlian
				</span>
				<h2 class="text-3xl font-extrabold text-brand-purple-dark">Fokus Pembelajaran Multimedia</h2>
				<p class="text-sm text-gray-400 font-medium">Kurikulum vokasi SMK Al Qodiriyah dirancang agar lulusan siap bekerja di industri kreatif digital.</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
				{#each innovations as inno}
					<div class="bg-[#fcfbfe] border border-purple-100/50 p-8 rounded-3xl space-y-3 hover:shadow-md transition-shadow">
						<div class="text-3xl">{inno.icon}</div>
						<h3 class="text-lg font-bold text-brand-purple-dark">{inno.title}</h3>
						<p class="text-xs text-gray-500 leading-relaxed font-medium">{inno.desc}</p>
					</div>
				{/each}
			</div>
		</div>

		<hr class="border-gray-100" />

		<!-- Info Sekolah Table -->
		<div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
			<div class="space-y-6">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Identitas Sekolah
				</span>
				<h2 class="text-2xl font-extrabold text-brand-purple-dark">Profil Resmi SMKS Al Qodiriyah</h2>
				<div class="space-y-3">
					{#each [
						{ label: 'Nama Sekolah', value: 'SMKS Al Qodiriyah Windusari' },
						{ label: 'NPSN', value: '69949720' },
						{ label: 'Status', value: 'Swasta (di bawah Yayasan)' },
						{ label: 'Akreditasi', value: 'B (BAN-S/M Kemdikbud RI)' },
						{ label: 'Kompetensi Keahlian', value: 'Multimedia' },
						{ label: 'Alamat', value: 'Jl. Lettu Sobandi Km.02, Dusun Bawang, Desa Candisari, Windusari, Magelang 56153' },
						{ label: 'Yayasan', value: 'Yayasan Al Qodiriyah Hasan Ibrahim' }
					] as row}
						<div class="flex gap-4 py-3 border-b border-gray-50">
							<span class="text-xs font-bold text-gray-400 w-40 shrink-0 uppercase tracking-wide">{row.label}</span>
							<span class="text-sm font-semibold text-gray-700">{row.value}</span>
						</div>
					{/each}
				</div>
			</div>
			
			<div class="space-y-6">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-teal-50 text-brand-teal border border-teal-100 uppercase tracking-wide">
					Pendaftaran
				</span>
				<h2 class="text-2xl font-extrabold text-brand-purple-dark">Bergabung Bersama Kami</h2>
				<p class="text-sm text-gray-500 leading-relaxed font-medium">
					SMK Al Qodiriyah membuka pendaftaran siswa baru setiap tahun ajaran. Calon siswa dapat mendaftar melalui sistem PPDB online atau langsung hadir ke sekretariat yayasan. Tersedia beasiswa bagi santri berprestasi dan keluarga kurang mampu.
				</p>
				<ul class="space-y-3 text-sm text-gray-600">
					{#each [
						'✅ Gratis biaya pendaftaran awal',
						'✅ Asrama pesantren tersedia lengkap',
						'✅ Bimbingan tahfidz & kitab kuning',
						'✅ Praktik industri di perusahaan mitra',
						'✅ Sertifikasi kompetensi keahlian multimedia'
					] as item}
						<li class="font-medium">{item}</li>
					{/each}
				</ul>
				<a 
					href="https://alqodiriyah.sch.id/ppdb2026" 
					class="btn bg-brand-purple hover:bg-brand-purple-dark text-white border-none font-bold rounded-xl px-8 w-full mt-4"
				>
					Daftar PPDB 2025/2026
				</a>
			</div>
		</div>

	</div>
</section>
