<script>
	const programs = [
		{ icon: '🌍', title: 'Bahasa Arab, Inggris & Jepang', desc: 'Program pembelajaran tiga bahasa asing secara intensif, mempersiapkan siswa berkomunikasi di era global.' },
		{ icon: '🎤', title: 'Pidato Tiga Bahasa', desc: 'Pelatihan public speaking dalam Bahasa Indonesia, Arab, dan Inggris untuk membentuk kepercayaan diri siswa.' },
		{ icon: '🥋', title: 'Pencak Silat', desc: 'Ekstrakurikuler bela diri tradisional PSHT untuk melatih fisik, kedisiplinan, dan karakter luhur siswa.' }
	];

	const achievements = [
		{ icon: '🏫', label: 'NPSN 69901347', sub: 'Kemendikdasmen RI' },
		{ icon: '📖', label: 'Kurikulum Terpadu', sub: 'Umum + Kepesantrenan' },
		{ icon: '🕌', label: 'Berbasis Pesantren', sub: 'Yayasan Al Qodiriyah' },
		{ icon: '🌱', label: 'Didirikan 2007', sub: 'Windusari, Magelang' }
	];

	const photos = [
		{
			src: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974714_x.jpg',
			alt: 'Gedung SMP Al Qodiriyah Windusari Magelang',
			caption: 'Gedung Sekolah'
		},
		{
			src: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974726_y-e1745139038743.jpg',
			alt: 'Pencak Silat PSHT SMP Al Qodiriyah',
			caption: 'Ekstrakurikuler Pencak Silat'
		},
		{
			src: 'https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974717_x.jpg',
			alt: 'Kegiatan Santri SMP Al Qodiriyah',
			caption: 'Kegiatan Santri'
		}
	];
</script>

<svelte:head>
	<title>SMP Al Qodiriyah Windusari Magelang – Pendidikan Islami Berbasis Pesantren</title>
	<meta name="description" content="SMP Al Qodiriyah Windusari Magelang (NPSN 69901347) adalah sekolah menengah pertama swasta di bawah Yayasan Al Qodiriyah Hasan Ibrahim. Mengintegrasikan kurikulum nasional dengan pendidikan pesantren, bahasa Arab, Inggris, Jepang, dan pencak silat." />
	<meta name="keywords" content="SMP Al Qodiriyah, Windusari Magelang, SMP pesantren Magelang, sekolah Islam Windusari, NPSN 69901347, SMP berbasis pesantren" />
</svelte:head>

<!-- Header Banner -->
<section
	class="relative py-28 bg-cover bg-center text-white"
	style="background-image: linear-gradient(rgba(88, 70, 140, 0.85), rgba(70, 55, 112, 0.92)), url('https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974714_x.jpg');"
>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-5">
		<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-white/20 text-white border border-white/30 uppercase tracking-wide">
			Pendidikan Menengah Pertama
		</span>
		<h1 class="text-4xl sm:text-5xl font-extrabold tracking-tight">SMP Al Qodiriyah</h1>
		<p class="text-purple-200 text-base font-semibold max-w-2xl mx-auto leading-relaxed">
			Sekolah Menengah Pertama Swasta Berbasis Pesantren dengan Kurikulum Terpadu di Windusari, Magelang, Jawa Tengah.
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
					Pendidikan Menengah
				</span>
				<h2 class="text-3xl font-extrabold text-brand-purple-dark tracking-tight">
					SMP Al Qodiriyah Windusari Magelang
				</h2>
				<p class="text-base text-gray-600 leading-relaxed font-medium">
					SMP Al Qodiriyah Windusari adalah sekolah menengah pertama swasta yang beralamat di Dusun Wahyurejo, Desa Candisari, Kecamatan Windusari, Kabupaten Magelang, Jawa Tengah. Sekolah ini berada di bawah naungan <strong>Yayasan Al Qodiriyah Hasan Ibrahim</strong>, satu yayasan dengan Pondok Pesantren Al Qodiriyah.
				</p>
				<p class="text-base text-gray-600 leading-relaxed font-medium">
					Dengan memadukan kurikulum nasional Kemendikbud dan materi kepesantrenan, SMP Al Qodiriyah membentuk generasi yang cerdas secara akademik sekaligus kuat dalam iman, akhlak, dan karakter Islami. Program unggulan mencakup pembelajaran tiga bahasa asing, pidato, dan pencak silat.
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
					src="https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974714_x.jpg"
					alt="Gedung SMP Al Qodiriyah Windusari Magelang"
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
				<h2 class="text-3xl font-extrabold text-brand-purple-dark">Potret Kegiatan SMP Al Qodiriyah</h2>
				<p class="text-sm text-gray-400 font-medium">Suasana belajar dan kegiatan santri/siswa SMP Al Qodiriyah Windusari.</p>
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

		<!-- Programs Grid -->
		<div class="space-y-12">
			<div class="text-center max-w-2xl mx-auto space-y-3">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Program Unggulan
				</span>
				<h2 class="text-3xl font-extrabold text-brand-purple-dark">Keunggulan SMP Al Qodiriyah</h2>
				<p class="text-sm text-gray-400 font-medium">Program khusus yang membedakan SMP Al Qodiriyah dari sekolah menengah pertama lainnya.</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
				{#each programs as prog}
					<div class="bg-[#fcfbfe] border border-purple-100/50 p-8 rounded-3xl space-y-3 hover:shadow-md transition-shadow">
						<div class="text-3xl">{prog.icon}</div>
						<h3 class="text-lg font-bold text-brand-purple-dark">{prog.title}</h3>
						<p class="text-xs text-gray-500 leading-relaxed font-medium">{prog.desc}</p>
					</div>
				{/each}
			</div>
		</div>

		<hr class="border-gray-100" />

		<!-- Identity Table + Registration -->
		<div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-start">
			<div class="space-y-6">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Identitas Sekolah
				</span>
				<h2 class="text-2xl font-extrabold text-brand-purple-dark">Profil Resmi SMP Al Qodiriyah</h2>
				<div class="space-y-3">
					{#each [
						{ label: 'Nama Sekolah', value: 'SMP Al Qodiriyah Windusari' },
						{ label: 'NPSN', value: '69901347' },
						{ label: 'Status', value: 'Swasta (di bawah Yayasan)' },
						{ label: 'Jenjang', value: 'Sekolah Menengah Pertama (SMP)' },
						{ label: 'Alamat', value: 'Dusun Wahyurejo, Desa Candisari, Windusari, Magelang 56152' },
						{ label: 'Kecamatan', value: 'Windusari, Kabupaten Magelang' },
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
					SMP Al Qodiriyah membuka pendaftaran siswa/santri baru setiap tahun ajaran. Calon siswa dapat mendaftar melalui PPDB online maupun hadir langsung ke sekretariat yayasan di Windusari, Magelang.
				</p>
				<ul class="space-y-3 text-sm text-gray-600">
					{#each [
						'✅ Asrama pesantren dan pembinaan 24 jam',
						'✅ Pembelajaran Al-Qur\'an dan kitab kuning',
						'✅ Program bahasa Arab, Inggris & Jepang',
						'✅ Kegiatan seni hadrah & pencak silat',
						'✅ Lingkungan asri, jauh dari kebisingan kota'
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
