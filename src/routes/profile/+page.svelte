<form>
	<div class="space-y-12 h-full">
		<div class="border-b border-white/10 pb-12">
			<h2 class="text-base md:text-2xl font-semibold leading-7 text-white">User Information</h2>
			<p class="mt-1 text-sm leading-6 text-gray-400">
				Upload your current information to upscale your product.
			</p>

			<div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
				<div class="col-span-full">
					<label for="photo" class="block text-sm font-medium leading-6 text-white">Photo</label>
					<div class="mt-2 flex items-center gap-x-3">
						<svg
							class="h-12 w-12 text-gray-500"
							viewBox="0 0 24 24"
							fill="currentColor"
							aria-hidden="true"
						>
							<path
								fill-rule="evenodd"
								d="M18.685 19.097A9.723 9.723 0 0021.75 12c0-5.385-4.365-9.75-9.75-9.75S2.25 6.615 2.25 12a9.723 9.723 0 003.065 7.097A9.716 9.716 0 0012 21.75a9.716 9.716 0 006.685-2.653zm-12.54-1.285A7.486 7.486 0 0112 15a7.486 7.486 0 015.855 2.812A8.224 8.224 0 0112 20.25a8.224 8.224 0 01-5.855-2.438zM15.75 9a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z"
								clip-rule="evenodd"
							/>
						</svg>
						<button
							type="button"
							class="rounded-md bg-white/10 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-white/20"
							>Change</button
						>
					</div>
				</div>

				<div class="sm:col-span-4">
					<label for="username" class="block text-sm font-medium leading-6 text-white"
						>Username</label
					>
					<div class="mt-2">
						<div
							class="flex rounded-md bg-white/5 ring-1 ring-inset ring-white/10 focus-within:ring-2 focus-within:ring-inset focus-within:ring-indigo-500"
						>
							<span class="flex select-none items-center pl-3 text-gray-500 sm:text-sm"
								>workcation.com/</span
							>
							<input
								type="text"
								name="username"
								id="username"
								autocomplete="username"
								class="flex-1 border-0 bg-transparent py-1.5 pl-1 text-white focus:ring-0 sm:text-sm sm:leading-6"
								placeholder="janesmith"
							/>
						</div>
					</div>
				</div>

				<div class="sm:col-span-3">
					<label for="last-name" class="block text-sm font-medium leading-6 text-white capitalize"
						>name</label
					>
					<div class="mt-2">
						<input
							type="text"
							name="last-name"
							id="last-name"
							autocomplete="family-name"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div>

				<div class="sm:col-span-4">
					<label for="email" class="block text-sm font-medium leading-6 text-white"
						>Email address</label
					>
					<div class="mt-2">
						<input
							id="email"
							name="email"
							type="email"
							autocomplete="email"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div>

				<div class="sm:col-span-4">
					<label for="email" class="block text-sm font-medium leading-6 text-white"
						>Brand name</label
					>
					<div class="mt-2">
						<input
							id="email"
							name="email"
							type="email"
							autocomplete="email"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div>

				<div class="sm:col-span-3">
					<label for="country" class="block text-sm font-medium leading-6 text-white"
						>Visibility</label
					>
					<div class="mt-2">
						<select
							id="country"
							name="country"
							autocomplete="country-name"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6 [&_*]:text-black"
						>
							<option>Private</option>
							<option>Public</option>
						</select>
					</div>
				</div>

				<!-- <div class="col-span-full">
					<label for="street-address" class="block text-sm font-medium leading-6 text-white"
						>Street address</label
					>
					<div class="mt-2">
						<input
							type="text"
							name="street-address"
							id="street-address"
							autocomplete="street-address"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div>

				<div class="sm:col-span-2 sm:col-start-1">
					<label for="city" class="block text-sm font-medium leading-6 text-white">City</label>
					<div class="mt-2">
						<input
							type="text"
							name="city"
							id="city"
							autocomplete="address-level2"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div>

				<div class="sm:col-span-2">
					<label for="region" class="block text-sm font-medium leading-6 text-white"
						>State / Province</label
					>
					<div class="mt-2">
						<input
							type="text"
							name="region"
							id="region"
							autocomplete="address-level1"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div>

				<div class="sm:col-span-2">
					<label for="postal-code" class="block text-sm font-medium leading-6 text-white"
						>ZIP / Postal code</label
					>
					<div class="mt-2">
						<input
							type="text"
							name="postal-code"
							id="postal-code"
							autocomplete="postal-code"
							class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-indigo-500 sm:text-sm sm:leading-6"
						/>
					</div>
				</div> -->
			</div>
		</div>
	</div>
	<div class="mt-6 flex items-center justify-end gap-x-6">
		<button type="button" class="text-sm font-semibold leading-6 text-white">Cancel</button>
		<button
			type="submit"
			class="rounded-md bg-indigo-500 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-400 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-500"
			>Save</button
		>
	</div>
</form>
