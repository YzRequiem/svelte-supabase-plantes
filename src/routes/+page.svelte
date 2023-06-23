<script>
	export let data;
	let { supabase } = data;
	$: ({ supabase } = data);

	let email ='' ;
	let password ='' ;

	const handleSignUp = async () => {
		try {
			await supabase.auth.signUp({
				email,
				password,
				options: {
					emailRedirectTo: `${location.origin}/auth/callback`
				}
			});
			
		} catch (error) {
			console.log('error', error);
		}
		
	};

	const handleSignIn = async () => {
		try {
				await supabase.auth.signInWithPassword({
					email,
					password
				});
		} catch (error) {
			console.log('Connexion failed ', error);
		}
	};

	const handleSignOut = async () => {
		try {
			
			await supabase.auth.signOut();
			console.log('deconnexion');
		} catch (error) {
			console.log('deconnexion failed', error);
		}
	};
</script>

<div class="container h-full mx-auto flex justify-center items-center">
	<div class="space-y-5">
		<form on:submit={handleSignUp} class="flex flex-col gap-10">
			<label class="label">
				<span>E-mail</span>
				<input bind:value={email} name="email" class="input" type="text" placeholder="Entrez votre adresse E-mail" />
			</label>
			<label class="label">
				<span>Mot de Passe </span>
				<input bind:value={password} title="password" name="password" class="input" type="password" placeholder="Entrez votre mot de passe" />
			</label>
	
			<button type="button" class="btn bg-gradient-to-br variant-gradient-tertiary-secondary">S'inscrire </button>

		</form>

		<button
			on:click={handleSignIn}
			class="btn bg-gradient-to-br variant-gradient-tertiary-secondary"
		>
			Se Connecter
		</button>
		<button
		on:click={handleSignOut}
		class="btn bg-gradient-to-br variant-gradient-tertiary-secondary"

		>
			Deconnexion 
		</button>
	</div>
</div>
