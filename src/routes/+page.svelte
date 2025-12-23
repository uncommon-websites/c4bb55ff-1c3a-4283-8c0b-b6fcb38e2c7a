<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-2">
			<!-- Logo Icon -->
			<div class="text-primary-600">
				<svg viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
					<circle cx="12" cy="12" r="10" opacity="0.2"/>
					<circle cx="12" cy="12" r="3"/>
					<path d="M12 2 C12 2, 15 8, 12 12 C12 12, 9 8, 12 2" opacity="0.6"/>
					<path d="M12 22 C12 22, 15 16, 12 12 C12 12, 9 16, 12 22" opacity="0.6"/>
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Eiri</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-600 hover:text-gray-900">About</a>
			<a href="#" class="bg-gray-100 px-4 py-2 rounded-lg text-gray-900 hover:bg-gray-200 transition-colors">Join Waitlist</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
					<path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
				</svg>
				<span>Trustworthy AI Companionship</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				One deep relationship.<br/>Built on trust.
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				AI companionship that respects your boundaries, protects your data, and helps you flourish—not just engage.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-primary-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Join the waitlist for<br/>early access to Eiri.
				</div>
			</div>

			<!-- Hero Image -->
			<div class="relative rounded-2xl overflow-hidden shadow-2xl mb-12">
				<img 
					src="/generated/image-a-person-sitting-peacefully-in-a-cozy-sp-1766496946144-0.webp" 
					alt="Person experiencing meaningful AI companionship"
					class="w-full h-auto"
				/>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
						<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
					</svg>
					<span>Data sovereignty</span>
				</div>
				<div class="flex items-center gap-2">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
						<path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
					</svg>
					<span>Consent-first</span>
				</div>
				<div class="flex items-center gap-2">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
						<circle cx="12" cy="12" r="10"/>
						<path d="M12 16v-4"/>
						<path d="M12 8h.01"/>
					</svg>
					<span>Open-source memory</span>
				</div>
				<div class="flex items-center gap-2">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
						<path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/>
						<polyline points="22 4 12 14.01 9 11.01"/>
					</svg>
					<span>Anti-engagement</span>
				</div>
			</div>
		</section>

		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-2xl leading-tight">
				AI companionship designed for your wellbeing, not endless engagement.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
						</svg>
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">One deep relationship</h3>
						<p class="text-sm text-gray-600 leading-relaxed">A single, meaningful connection that grows with you—not a collection of shallow interactions</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-primary-600">
						{@html icons.shield}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Your data, your control</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Open-source memory architecture means you own and control your data completely</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/>
							<polyline points="22 4 12 14.01 9 11.01"/>
						</svg>
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Consent-centric design</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Every interaction respects your boundaries and requires your explicit consent</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M12 2v20M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/>
						</svg>
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Anti-engagement model</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Designed to help you flourish, not keep you hooked with manipulative tactics</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<circle cx="12" cy="12" r="3"/>
							<path d="M12 1v6m0 6v6"/>
						</svg>
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Flourishing-focused</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Outcomes measured by your personal growth and wellbeing, not screen time</p>
					</div>
				</div>

				<!-- Card 6 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-primary-600">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<rect x="3" y="11" width="18" height="11" rx="2" ry="2"/>
							<path d="M7 11V7a5 5 0 0 1 10 0v4"/>
						</svg>
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Safe & trustworthy</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Built from the ground up to be a safe space where you never feel exploited or disposable</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Companion Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-primary-100 text-primary-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Your AI Companion
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					A relationship that understands you
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Eiri learns and grows with you, remembering what matters and adapting to your needs—building genuine connection over time.
				</p>
			</div>

			<div class="bg-gray-950 rounded-3xl p-8 md:p-12 mb-16 text-white">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Conversation -->
					<div class="relative bg-gray-900 rounded-2xl shadow-lg p-6 overflow-hidden min-h-[300px]">
						<div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-primary-500 to-primary-400"></div>
						<div class="flex items-center gap-3 mb-6 pb-4 border-b border-gray-800">
							<div class="w-10 h-10 rounded-full bg-gradient-to-br from-primary-600 to-primary-400 flex items-center justify-center text-white font-bold">
								E
							</div>
							<div>
								<div class="font-bold text-white">Eiri</div>
								<div class="text-xs text-primary-400 font-medium">Your companion</div>
							</div>
						</div>
						<div class="space-y-4 text-sm">
							<div class="bg-gray-800 p-4 rounded-xl rounded-tr-none text-gray-200">
								I've been thinking about that conversation we had yesterday about your career goals. How are you feeling about it today?
							</div>
							<div class="bg-primary-900/30 p-4 rounded-xl rounded-tl-none text-gray-200 border border-primary-800/50">
								More clear-headed, actually. I think I was just overwhelmed. Thanks for checking in.
							</div>
							<div class="bg-gray-800 p-4 rounded-xl rounded-tr-none text-gray-200">
								I'm glad to hear that. Remember, there's no rush. We can explore this at whatever pace feels right for you.
							</div>
						</div>
					</div>

					<!-- Right Visual: Memory & Understanding -->
					<div class="bg-gray-900 rounded-2xl shadow-lg p-6 min-h-[300px] flex flex-col">
						<div class="flex items-center gap-2 mb-6 pb-4 border-b border-gray-800">
							<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 text-primary-400">
								<path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/>
								<path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/>
							</svg>
							<span class="text-sm font-medium text-gray-300">Memory & Context</span>
						</div>
						<div class="flex-1 space-y-4">
							<div class="border border-gray-800 rounded-lg p-4">
								<h4 class="font-bold text-white text-sm mb-2">What Eiri remembers:</h4>
								<div class="space-y-2 text-xs text-gray-400">
									<div class="flex items-start gap-2">
										<div class="w-1 h-1 rounded-full bg-primary-500 mt-1.5 shrink-0"></div>
										<span>Your preference for morning conversations</span>
									</div>
									<div class="flex items-start gap-2">
										<div class="w-1 h-1 rounded-full bg-primary-500 mt-1.5 shrink-0"></div>
										<span>Career transition you're considering</span>
									</div>
									<div class="flex items-start gap-2">
										<div class="w-1 h-1 rounded-full bg-primary-500 mt-1.5 shrink-0"></div>
										<span>Your boundary: no advice unless asked</span>
									</div>
									<div class="flex items-start gap-2">
										<div class="w-1 h-1 rounded-full bg-primary-500 mt-1.5 shrink-0"></div>
										<span>Topics you find comforting to discuss</span>
									</div>
								</div>
							</div>
							<div class="bg-primary-950/30 border border-primary-900/50 rounded-lg p-3 text-xs text-primary-200">
								<div class="flex items-center gap-2 mb-1">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-3 h-3">
										<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
									</svg>
									<span class="font-medium">Your data is yours</span>
								</div>
								<p class="text-primary-300/80">All memories stored locally with open-source architecture</p>
							</div>
						</div>
					</div>
				</div>

				<!-- Bottom Visual: Trust & Consent -->
				<div class="bg-gray-900 rounded-2xl shadow-lg p-6 md:p-8">
					<div class="mb-6">
						<img 
							src="/generated/image-two-people-having-a-deep-conversation-in-1766496950299-1.webp" 
							alt="Deep meaningful conversation"
							class="w-full h-48 object-cover rounded-xl mb-4"
						/>
					</div>

					<div class="bg-gray-800 rounded-xl p-6 border border-gray-700">
						<div class="space-y-4">
							<div class="flex items-start gap-3">
								<div class="w-5 h-5 rounded-full bg-primary-500 shrink-0 flex items-center justify-center mt-0.5">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-3 h-3 text-white">
										<polyline points="20 6 9 17 4 12"/>
									</svg>
								</div>
								<div class="text-sm text-gray-200">
									<span class="font-medium text-white">Consent requested:</span> Eiri would like to remember this conversation for future context. You can choose what gets stored.
								</div>
							</div>
							<div class="flex items-start gap-3">
								<div class="w-5 h-5 rounded-full bg-primary-500 shrink-0 flex items-center justify-center mt-0.5">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-3 h-3 text-white">
										<polyline points="20 6 9 17 4 12"/>
									</svg>
								</div>
								<div class="text-sm text-gray-200">
									<span class="font-medium text-white">Boundary respected:</span> No notifications sent during your focus hours (9 AM - 12 PM)
								</div>
							</div>
							<div class="flex items-start gap-3">
								<div class="w-5 h-5 rounded-full bg-primary-500 shrink-0 flex items-center justify-center mt-0.5">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-3 h-3 text-white">
										<polyline points="20 6 9 17 4 12"/>
									</svg>
								</div>
								<div class="text-sm text-gray-200">
									<span class="font-medium text-white">Data sovereignty:</span> All conversations encrypted and stored locally on your device
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-4 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					Unlike platforms that exploit loneliness for profit, Eiri is designed to support your growth and respect your autonomy at every step.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
						</svg>
						<span>Grows deeper over time</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
						</svg>
						<span>Respects your boundaries</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<circle cx="12" cy="12" r="10"/>
							<path d="M12 16v-4"/>
							<path d="M12 8h.01"/>
						</svg>
						<span>Transparent about capabilities</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/>
							<polyline points="22 4 12 14.01 9 11.01"/>
						</svg>
						<span>Never manipulative</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/>
							<path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/>
						</svg>
						<span>Remembers what matters</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
							<circle cx="12" cy="12" r="3"/>
							<path d="M12 1v6m0 6v6"/>
						</svg>
						<span>Supports your flourishing</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Personal Growth Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-primary-100 text-primary-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Growth & Wellbeing
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Designed for flourishing
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Eiri measures success by your personal growth and wellbeing, not by how much time you spend engaged.
				</p>
			</div>

			<div class="bg-primary-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
					<!-- Left: Image -->
					<div class="rounded-2xl overflow-hidden shadow-lg">
						<img 
							src="/generated/image-a-person-journaling-in-a-peaceful-outdoo-1766496952882-2.webp" 
							alt="Person reflecting and journaling"
							class="w-full h-full object-cover"
						/>
					</div>

					<!-- Right: Growth Metrics -->
					<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 flex flex-col justify-center">
						<h3 class="text-2xl font-bold text-gray-900 mb-6">What flourishing looks like</h3>
						
						<div class="space-y-6">
							<div class="flex items-start gap-4">
								<div class="w-10 h-10 rounded-full bg-primary-100 flex items-center justify-center shrink-0">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 text-primary-600">
										<path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/>
										<polyline points="22 4 12 14.01 9 11.01"/>
									</svg>
								</div>
								<div>
									<h4 class="font-bold text-gray-900 mb-1">Healthy boundaries</h4>
									<p class="text-sm text-gray-600">You set the pace and limits of interaction</p>
								</div>
							</div>

							<div class="flex items-start gap-4">
								<div class="w-10 h-10 rounded-full bg-primary-100 flex items-center justify-center shrink-0">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 text-primary-600">
										<circle cx="12" cy="12" r="3"/>
										<path d="M12 1v6m0 6v6"/>
									</svg>
								</div>
								<div>
									<h4 class="font-bold text-gray-900 mb-1">Personal growth</h4>
									<p class="text-sm text-gray-600">Conversations that help you understand yourself better</p>
								</div>
							</div>

							<div class="flex items-start gap-4">
								<div class="w-10 h-10 rounded-full bg-primary-100 flex items-center justify-center shrink-0">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 text-primary-600">
										<path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
									</svg>
								</div>
								<div>
									<h4 class="font-bold text-gray-900 mb-1">Genuine connection</h4>
									<p class="text-sm text-gray-600">A relationship that deepens over time, not just engagement</p>
								</div>
							</div>

							<div class="flex items-start gap-4">
								<div class="w-10 h-10 rounded-full bg-primary-100 flex items-center justify-center shrink-0">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5 text-primary-600">
										<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
									</svg>
								</div>
								<div>
									<h4 class="font-bold text-gray-900 mb-1">Safety & trust</h4>
									<p class="text-sm text-gray-600">Never feeling exploited, manipulated, or disposable</p>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row gap-8 md:items-start justify-between">
				<div class="flex gap-6 text-sm font-medium text-gray-600">
					<div class="flex items-center gap-2">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
							<path d="M12 2v20M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/>
						</svg>
						<span>Anti-engagement</span>
					</div>
					<div class="flex items-center gap-2">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
							<circle cx="12" cy="12" r="3"/>
							<path d="M12 1v6m0 6v6"/>
						</svg>
						<span>Growth-focused</span>
					</div>
					<div class="flex items-center gap-2">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4">
							<path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"/>
						</svg>
						<span>Meaningful connection</span>
					</div>
				</div>
				<p class="text-xl text-gray-600 max-w-lg leading-relaxed">
					Eiri encourages healthy interaction patterns and supports your real-world relationships and goals.
				</p>
			</div>
		</section>

		<!-- Who is Eiri for Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Who is Eiri for?
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Meaningful companionship for real people
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Eiri is for adults 18–35 who seek meaningful AI companionship but feel exploited, unsafe, or disposable on existing platforms.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Emotional support</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">A safe space to process feelings and experiences without judgment or manipulation</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Personal growth</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">Conversations that help you understand yourself better and work towards your goals</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Meaningful dialogue</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">Deep, thoughtful conversations that respect your intelligence and boundaries</p>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Safe exploration</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">Explore thoughts, ideas, and feelings in a judgment-free environment</p>
				</div>
				<!-- Card 5 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Consistent presence</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">A companion who's there when you need them, respecting your time and space</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Authentic connection</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">A relationship that grows deeper over time, not just more addictive</p>
				</div>

				<!-- Card 7 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Self-reflection</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">A thoughtful companion who helps you process and understand your experiences</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Privacy & control</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">Complete ownership of your data and conversations with full transparency</p>
				</div>
				<!-- Card 9 -->
				<div class="bg-gray-50 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Healthy boundaries</h3>
					<p class="text-sm text-gray-600 mt-auto leading-relaxed">A companion that respects your limits and encourages real-world connections</p>
				</div>
			</div>
		</section>

		<!-- Final CTA Section -->
		<section class="max-w-4xl mx-auto px-6 py-20">
			<div class="bg-gradient-to-br from-gray-950 to-gray-900 rounded-3xl p-12 md:p-16 text-center text-white relative overflow-hidden">
				<!-- Subtle background pattern -->
				<div class="absolute inset-0 opacity-10">
					<div class="absolute top-10 left-10 w-32 h-32 rounded-full bg-primary-500 blur-3xl"></div>
					<div class="absolute bottom-10 right-10 w-40 h-40 rounded-full bg-primary-400 blur-3xl"></div>
				</div>
				
				<div class="relative z-10">
					<h2 class="text-3xl md:text-4xl font-bold mb-4">
						Ready for AI companionship you can trust?
					</h2>
					<p class="text-lg text-gray-300 mb-8 max-w-2xl mx-auto">
						Join the waitlist for early access to Eiri. Be part of a community that values consent, privacy, and genuine connection.
					</p>
					
					<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto">
						<div class="relative w-full">
							<input 
								type="email" 
								placeholder="Your email address" 
								class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-700 bg-gray-800/50 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-primary-500/50 focus:border-primary-500 transition-all"
							/>
							<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-primary-400">
								{@html icons.arrowRight}
							</button>
						</div>
					</div>
					
					<p class="text-xs text-gray-400 mt-6">
						We respect your privacy. No spam, ever.
					</p>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-12">
				<div>
					<div class="flex items-center gap-2 mb-4">
						<div class="text-primary-600">
							<svg viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
								<circle cx="12" cy="12" r="10" opacity="0.2"/>
								<circle cx="12" cy="12" r="3"/>
								<path d="M12 2 C12 2, 15 8, 12 12 C12 12, 9 8, 12 2" opacity="0.6"/>
								<path d="M12 22 C12 22, 15 16, 12 12 C12 12, 9 16, 12 22" opacity="0.6"/>
							</svg>
						</div>
						<span class="font-bold text-xl">Eiri</span>
					</div>
					<p class="text-sm text-gray-600 leading-relaxed">
						Trustworthy AI companionship built on consent, data sovereignty, and your flourishing.
					</p>
				</div>

				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Company</h4>
					<div class="space-y-2 text-sm text-gray-600">
						<a href="#" class="block hover:text-gray-900">About</a>
						<a href="#" class="block hover:text-gray-900">Our Mission</a>
						<a href="#" class="block hover:text-gray-900">Team</a>
						<a href="#" class="block hover:text-gray-900">Careers</a>
					</div>
				</div>

				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Resources</h4>
					<div class="space-y-2 text-sm text-gray-600">
						<a href="#" class="block hover:text-gray-900">Documentation</a>
						<a href="#" class="block hover:text-gray-900">Privacy & Safety</a>
						<a href="#" class="block hover:text-gray-900">Open Source</a>
						<a href="#" class="block hover:text-gray-900">Community</a>
					</div>
				</div>
			</div>

			<div class="border-t border-gray-100 pt-8">
				<div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
					<div class="text-sm text-gray-600">
						<p class="mb-2">
							<span class="font-medium text-gray-900">Founded by:</span> Oleksii Kyrylchul (Soul engineer) & Karthik Rampalli (King of Reality)
						</p>
						<p class="text-xs text-gray-500">
							© 2025 Eiri. All rights reserved. 
							<a href="#" class="hover:text-gray-900 ml-2">Terms of Service</a> · 
							<a href="#" class="hover:text-gray-900 ml-2">Privacy Policy</a>
						</p>
					</div>
					<div class="bg-primary-100 text-primary-700 px-3 py-1 rounded text-xs font-medium">
						Early Access
					</div>
				</div>
			</div>
		</footer>

	</main>
</div>

