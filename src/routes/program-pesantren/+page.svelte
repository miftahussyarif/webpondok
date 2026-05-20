<script>
	const coreCurriculums = [
		{ title: 'Program Tahfidz Al-Qur’an', desc: 'Menghafal Al-Qur’an dengan bimbingan ustadz mutakhassis (spesialis), berfokus pada tajwid dan kelancaran setoran hafalan.' },
		{ title: 'Kajian Kitab Kuning (Salaf)', desc: 'Pengkajian kitab kuning klasik dalam bidang Fiqih, Nahwu-Shorof, Hadits, Tafsir Jalalain, dan akhlak Tasawuf.' },
		{ title: 'Pendidikan Formal Terpadu', desc: 'Kurikulum Nasional Kemendikbudristek untuk SMP & SMK Al Qodiriyah dengan fokus kejuruan Multimedia/Digital.' }
	];

	const highlights = [
		{ title: 'Awesome Support', desc: 'Bimbingan dan pendampingan santri 24 jam penuh oleh para pengurus senior dan dewan asatidzah.' },
		{ title: 'Financial Advise', desc: 'Manajemen keuangan dan beasiswa santri berprestasi serta keringanan bagi keluarga yatim/piatu.' },
		{ title: 'Social Sharing', desc: 'Santri dididik terjun langsung berdakwah dan membina kemasyarakatan di lingkungan desa Windusari.' },
		{ title: 'SEO Optimized', desc: 'Kurikulum Multimedia SMK mempersiapkan santri menguasai optimasi web dan digital marketing.' },
		{ title: 'Supreme Choice', desc: 'Lingkungan pesantren yang asri, jauh dari kebisingan kota, ideal untuk konsentrasi belajar.' },
		{ title: 'Market Analysis', desc: 'Penyelarasan program vokasi SMK dengan kebutuhan dunia industri kerja dan kewirausahaan modern.' }
	];
</script>

<svelte:head>
	<title>Program Pesantren – Ponpes Al Qodiriyah</title>
</svelte:head>

<!-- Header Banner -->
<section 
	class="relative py-24 bg-cover bg-center text-white" 
	style="background-image: linear-gradient(rgba(88, 70, 140, 0.8), rgba(70, 55, 112, 0.9)), url('https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974721_y.jpg');"
>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-4">
		<h1 class="text-4xl font-extrabold tracking-tight">Program Pendidikan</h1>
		<p class="text-purple-200 text-sm font-semibold max-w-xl mx-auto">
			Program Unggulan Pesantren Al Qodiriyah Hasan Ibrahim Windusari Magelang.
		</p>
	</div>
</section>

<!-- Core Programs -->
<section class="py-24 bg-white">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-20">
		<div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
			{#each coreCurriculums as cc, i}
				<div class="bg-[#fcfbfe] border border-purple-100 p-8 rounded-3xl space-y-4 hover:shadow-lg transition-shadow">
					<span class="inline-flex items-center justify-center w-10 h-10 rounded-xl bg-brand-purple text-white font-bold text-sm">
						0{i + 1}
					</span>
					<h3 class="text-xl font-bold text-brand-purple-dark">{cc.title}</h3>
					<p class="text-sm text-gray-600 leading-relaxed font-medium">{cc.desc}</p>
				</div>
			{/each}
		</div>

		<hr class="border-gray-100" />

		<!-- Qode Template Features styled beautifully -->
		<div class="space-y-12">
			<div class="text-center max-w-2xl mx-auto space-y-3">
				<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
					Keunggulan Kami
				</span>
				<h2 class="text-3xl font-extrabold text-brand-purple-dark">Fasilitas & Layanan Pendidikan</h2>
				<p class="text-sm text-gray-400 font-medium">Aspek pendukung untuk menjamin proses pembelajaran santri berjalan dengan optimal.</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
				{#each highlights as hl}
					<div class="p-8 rounded-3xl border border-gray-100 bg-white hover:border-brand-purple/20 shadow-sm hover:shadow-md transition-all duration-300 space-y-4">
						<div class="w-12 h-12 rounded-2xl bg-purple-50 flex items-center justify-center text-brand-purple text-xl">
							{#if hl.title.includes('Support')}
								🤝
							{:else if hl.title.includes('Financial')}
								💼
							{:else if hl.title.includes('Social')}
								📣
							{:else if hl.title.includes('SEO')}
								🚀
							{:else if hl.title.includes('Supreme')}
								🌟
							{:else}
								📊
							{/if}
						</div>
						<h3 class="text-lg font-bold text-brand-purple-dark">{hl.title}</h3>
						<p class="text-xs text-gray-500 leading-relaxed font-medium">{hl.desc}</p>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
