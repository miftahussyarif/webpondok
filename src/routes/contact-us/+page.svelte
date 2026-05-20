<script>
	let name = $state('');
	let email = $state('');
	let subject = $state('');
	let message = $state('');
	let statusMsg = $state('');
	let isSubmitting = $state(false);

	function handleSubmit(e) {
		e.preventDefault();
		isSubmitting = true;
		statusMsg = '';
		
		setTimeout(() => {
			isSubmitting = false;
			statusMsg = 'Pesan Anda telah berhasil dikirim! Kami akan menghubungi Anda segera.';
			name = '';
			email = '';
			subject = '';
			message = '';
		}, 1500);
	}
</script>

<svelte:head>
	<title>Hubungi Kami – Ponpes Al Qodiriyah</title>
</svelte:head>

<!-- Header Banner -->
<section 
	class="relative py-24 bg-cover bg-center text-white" 
	style="background-image: linear-gradient(rgba(88, 70, 140, 0.8), rgba(70, 55, 112, 0.9)), url('https://image.alqodiriyah.sch.id/wp-content/uploads/2025/04/photo_6064441458166974717_x.jpg');"
>
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-4">
		<h1 class="text-4xl font-extrabold tracking-tight">Hubungi Kami</h1>
		<p class="text-purple-200 text-sm font-semibold max-w-xl mx-auto">
			Punya pertanyaan seputar pendaftaran santri baru atau program kami? Hubungi kami langsung.
		</p>
	</div>
</section>

<section class="py-24 bg-white">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-16">
		
		<div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-stretch">
			<!-- Contact info column -->
			<div class="lg:col-span-5 space-y-8 flex flex-col justify-between">
				<div class="space-y-6">
					<span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold bg-purple-50 text-brand-purple border border-purple-100 uppercase tracking-wide">
						Informasi Kontak
					</span>
					<h2 class="text-3xl font-extrabold text-brand-purple-dark tracking-tight">
						Mari Berkunjung ke Pesantren Kami
					</h2>
					<p class="text-sm text-gray-500 leading-relaxed font-medium">
						Kami menyambut dengan hangat kedatangan wali santri dan calon santri untuk bersilaturahmi langsung dengan pengasuh pondok.
					</p>
				</div>

				<div class="space-y-6 py-4">
					<!-- Address Card -->
					<div class="flex items-start gap-4">
						<div class="w-10 h-10 rounded-xl bg-purple-50 flex items-center justify-center text-brand-purple text-lg shrink-0">
							📍
						</div>
						<div>
							<h4 class="text-sm font-bold text-brand-purple-dark">Alamat Pesantren</h4>
							<p class="text-xs text-gray-500 mt-1 leading-relaxed">
								Bawang, Candisari, Windusari,<br />Magelang, Jawa Tengah 56152
							</p>
						</div>
					</div>

					<!-- WhatsApp Card -->
					<div class="flex items-start gap-4">
						<div class="w-10 h-10 rounded-xl bg-emerald-50 flex items-center justify-center text-emerald-600 text-lg shrink-0">
							💬
						</div>
						<div class="space-y-2">
							<h4 class="text-sm font-bold text-brand-purple-dark">Layanan WhatsApp (Hotline)</h4>
							<div class="flex flex-wrap gap-2">
								<a 
									href="https://wa.me/628123456789?text=Assalamualaikum%20admin%20putra" 
									target="_blank" 
									rel="noopener noreferrer" 
									class="btn btn-sm bg-emerald-600 hover:bg-emerald-700 text-white border-none font-bold rounded-lg"
								>
									Hubungi Putra
								</a>
								<a 
									href="https://wa.me/628123456789?text=Assalamualaikum%20admin%20putri" 
									target="_blank" 
									rel="noopener noreferrer" 
									class="btn btn-sm bg-emerald-600 hover:bg-emerald-700 text-white border-none font-bold rounded-lg"
								>
									Hubungi Putri
								</a>
							</div>
						</div>
					</div>

					<!-- Email Card -->
					<div class="flex items-start gap-4">
						<div class="w-10 h-10 rounded-xl bg-purple-50 flex items-center justify-center text-brand-purple text-lg shrink-0">
							✉️
						</div>
						<div>
							<h4 class="text-sm font-bold text-brand-purple-dark">Email Resmi</h4>
							<a href="mailto:ponpesalqodiriyah@gmail.com" class="text-xs text-brand-purple hover:underline mt-1 block">
								ponpesalqodiriyah@gmail.com
							</a>
						</div>
					</div>
				</div>

				<div class="text-xs text-gray-400 font-medium">
					Jam Kerja Sekretariat: 08:00 - 16:00 WIB (Setiap Hari)
				</div>
			</div>

			<!-- Contact Form Column -->
			<div class="lg:col-span-7 bg-[#fcfbfe] border border-purple-100/50 p-8 sm:p-12 rounded-3xl shadow-sm space-y-6">
				<h3 class="text-xl font-bold text-brand-purple-dark">Kirimkan Pesan</h3>

				{#if statusMsg}
					<div class="alert alert-success bg-emerald-50 text-emerald-800 border border-emerald-200 rounded-2xl p-4 text-sm font-semibold">
						{statusMsg}
					</div>
				{/if}

				<form onsubmit={handleSubmit} class="space-y-5">
					<div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
						<div class="space-y-1.5">
							<label for="frm-name" class="text-xs font-bold text-gray-500">Nama Lengkap</label>
							<input 
								id="frm-name" 
								type="text" 
								required 
								bind:value={name}
								placeholder="Nama Anda..." 
								class="input input-bordered w-full bg-white border-gray-200 rounded-xl text-sm" 
							/>
						</div>
						<div class="space-y-1.5">
							<label for="frm-email" class="text-xs font-bold text-gray-500">Alamat Email</label>
							<input 
								id="frm-email" 
								type="email" 
								required 
								bind:value={email}
								placeholder="Email Anda..." 
								class="input input-bordered w-full bg-white border-gray-200 rounded-xl text-sm" 
							/>
						</div>
					</div>

					<div class="space-y-1.5">
						<label for="frm-subject" class="text-xs font-bold text-gray-500">Subjek / Topik</label>
						<input 
							id="frm-subject" 
							type="text" 
							required 
							bind:value={subject}
							placeholder="Tanya Pendaftaran Santri, Kerja Sama, dll..." 
							class="input input-bordered w-full bg-white border-gray-200 rounded-xl text-sm" 
						/>
					</div>

					<div class="space-y-1.5">
						<label for="frm-msg" class="text-xs font-bold text-gray-500">Isi Pesan</label>
						<textarea 
							id="frm-msg" 
							rows="5" 
							required 
							bind:value={message}
							placeholder="Tulis pesan Anda di sini..." 
							class="textarea textarea-bordered w-full bg-white border-gray-200 rounded-xl text-sm"
						></textarea>
					</div>

					<button 
						type="submit" 
						disabled={isSubmitting}
						class="btn bg-brand-purple hover:bg-brand-purple-dark text-white border-none w-full rounded-xl font-bold transition-all shadow-md cursor-pointer"
					>
						{#if isSubmitting}
							Mengirim...
						{:else}
							Kirim Pesan
						{/if}
					</button>
				</form>
			</div>
		</div>

		<hr class="border-gray-100" />

		<!-- Maps embed section -->
		<div class="space-y-6">
			<h3 class="text-xl font-bold text-brand-purple-dark text-center">Lokasi Ponpes Al Qodiriyah</h3>
			<div class="w-full h-96 rounded-3xl overflow-hidden shadow-md border border-gray-100">
				<iframe 
					title="Lokasi SMK & Ponpes Al Qodiriyah Windusari Magelang"
					src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3956.6223811422724!2d110.16972137588172!3d-7.396140072821397!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e7a849c039af7bd%3A0xf9e9fec9cc805c82!2sSMK%20AL-QODIRIYAH%20WINDUSARI!5e0!3m2!1sen!2sid!4v1779308997994!5m2!1sen!2sid" 
					class="w-full h-full border-none"
					allowfullscreen="" 
					loading="lazy" 
					referrerpolicy="no-referrer-when-downgrade"
				></iframe>
			</div>
		</div>

	</div>
</section>
