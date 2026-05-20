<script>
	// Testimony items (Wali Santri or Alumnus)
	const testimonials = [
		{
			quote: "Alhamdulillah, setelah belajar di Ponpes Al Qodiriyah, anak kami tidak hanya menguasai pelajaran sekolah umum di SMK, tetapi juga memiliki akhlak yang baik dan rajin membaca Al-Qur'an serta kitab kuning.",
			author: "H. Ahmad Syafii",
			role: "Wali Santri (Magelang)"
		},
		{
			quote: "Kombinasi sistem salafiyah dan pendidikan formal berbasis digital (multimedia) memberikan bekal yang sangat komprehensif bagi saya untuk melanjutkan studi dan bekerja.",
			author: "Erin Smith (Foton Demo)",
			role: "Alumni / Web Developer"
		}
	];
</script>

<svelte:head>
	<title>Sekapur Sirih (Profil Singkat) – Ponpes Al Qodiriyah</title>
</svelte:head>

<!-- Header Banner -->
<section 
	class="relative py-24 bg-cover bg-center text-white" 
	style="background-image: linear-gradient(rgba(88, 70, 140, 0.8), rgba(70, 55, 112, 0.9)), url('https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974715_y-1.jpg');"
>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-4">
		<h1 class="text-4xl font-extrabold tracking-tight">Sekapur Sirih</h1>
		<p class="text-purple-200 text-sm font-semibold max-w-xl mx-auto">
			Sambutan dan Profil Singkat Pondok Pesantren Al Qodiriyah Windusari Magelang.
		</p>
	</div>
</section>

<!-- Content Section -->
<section class="py-24 bg-white">
	<div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 space-y-16">
		
		<!-- Introduction card -->
		<div class="grid grid-cols-1 md:grid-cols-12 gap-12 items-start">
			<!-- Image left side -->
			<div class="md:col-span-5 relative">
				<img 
					src="https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974717_x.jpg" 
					alt="Romo KH. Idris Syafe'i Marzuki" 
					class="w-full h-auto rounded-3xl object-cover shadow-xl border border-gray-100"
				/>
				<div class="absolute -bottom-6 -right-6 bg-brand-teal text-brand-purple-dark p-6 rounded-2xl shadow-lg max-w-xs hidden sm:block">
					<span class="block text-xs font-bold uppercase tracking-wider opacity-85">Didirikan Sejak</span>
					<span class="block text-3xl font-extrabold mt-1">2005</span>
				</div>
			</div>
			
			<!-- Text right side -->
			<div class="md:col-span-7 space-y-6">
				<h2 class="text-2xl sm:text-3xl font-extrabold text-brand-purple-dark tracking-tight leading-tight">
					Ngaji + Sekolah? Al-Qodiriyah Aja!
				</h2>
				<span class="inline-block text-sm font-semibold text-brand-teal bg-teal-50 px-3.5 py-1.5 rounded-full border border-teal-100">
					Teguh dalam Iman, Sholeh dan memiliki mental Spiritual.
				</span>
				<div class="space-y-4 text-gray-600 leading-relaxed font-medium text-sm sm:text-base">
					<p>
						Pondok Pesantren Al Qodiriyah didirikan pada tahun 2005 oleh <strong>KH. Muhammad Idris Syafe'i Marzuki</strong> bin KH. Maksum bin KH. Masturin bin Kyai Muhammad Rasch bin Syaikh Hasan Ibrahim (Mbah Wali Parakan). Yayasan ini kemudian berbadan hukum resmi pada tanggal 7 November 2007 di hadapan notaris Kunsri Hastuti, S.H.
					</p>
					<p>
						Berlokasi di <strong>Jl. Lettu Sobandi Km. 02, Bawang, Desa Candisari, Kecamatan Windusari, Kabupaten Magelang, Jawa Tengah</strong>, pesantren ini didirikan dengan tujuan utama mencetak kader generasi muslim yang berilmu, berakhlak mulia, dan tangguh menghadapi tantangan zaman modern. Untuk mendukung program wajib belajar dan pendidikan komprehensif, pada tahun 2012 didirikan Yayasan Al Qodiriyah Hasan Ibrahim guna menaungi lembaga pendidikan formal di lingkungan pesantren.
					</p>
					<p>
						Pondok Pesantren Al Qodiriyah Magelang secara apik memadukan sistem pembelajaran pesantren salaf (klasik) dengan sekolah formal berbasis digital (multimedia). Para santri tidak hanya belajar pengetahuan umum dan teknologi, tetapi juga difokuskan untuk mengkaji kitab-kitab kuning. Pembelajaran kitab diajarkan secara berjenjang, mulai dari ilmu Nahwu-Shorof (tata bahasa Arab), Hadits, Tafsir, Fiqih, hingga penguatan batin melalui Tauhid dan Tasawuf.
					</p>
					
					<div class="pt-6">
						<a 
							href="https://alqodiriyah.sch.id/ppdb2026/" 
							class="inline-flex items-center justify-center gap-2 px-6 py-3.5 bg-brand-purple text-white font-bold rounded-xl shadow-lg shadow-brand-purple/20 hover:bg-brand-purple-dark hover:shadow-brand-purple/40 hover:-translate-y-0.5 transition-all w-full sm:w-auto"
						>
							<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
								<path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-8.707l-3-3a1 1 0 00-1.414 1.414L10.586 9H7a1 1 0 100 2h3.586l-1.293 1.293a1 1 0 101.414 1.414l3-3a1 1 0 000-1.414z" clip-rule="evenodd" />
							</svg>
							Daftar Santri Baru (PPDB) Sekarang
						</a>
						<p class="mt-3 text-xs text-gray-500 font-semibold">* Klik untuk diarahkan ke halaman resmi pendaftaran PPDB Al Qodiriyah.</p>
					</div>
				</div>
			</div>
		</div>

		<!-- Divider line -->
		<hr class="border-gray-100" />

		<!-- Testimonial Section -->
		<div class="space-y-12">
			<div class="text-center max-w-2xl mx-auto space-y-3">
				<h3 class="text-2xl font-extrabold text-brand-purple-dark">Apa Kata Mereka?</h3>
				<p class="text-sm text-gray-400 font-medium">Ulasan dari alumni dan wali santri yang belajar bersama kami.</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
				{#each testimonials as test}
					<div class="bg-[#fcfbfe] p-8 rounded-3xl border border-purple-100/50 shadow-sm hover:shadow-md transition-shadow relative">
						<span class="absolute top-6 left-6 text-7xl text-purple-200/40 font-serif leading-none">“</span>
						<div class="relative space-y-6 pt-4">
							<p class="text-sm text-gray-600 leading-relaxed font-medium italic">
								{test.quote}
							</p>
							<div class="flex items-center gap-3">
								<div class="w-10 h-10 rounded-full bg-brand-purple-light/20 flex items-center justify-center font-bold text-brand-purple text-sm">
									{test.author[0]}
								</div>
								<div>
									<h4 class="text-sm font-bold text-brand-purple-dark">{test.author}</h4>
									<p class="text-xs text-gray-400 font-semibold">{test.role}</p>
								</div>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>

	</div>
</section>
