[[Bases Numéricas|]][[Algoritmos|]][[Comportamento Asintótico das funções|]][[Congruências e Aritmética Modular|]]
![[Aula 11.1-Exponenciação Binária.mp4]]

---
![[Pasted image 20211220192923.png]]

```Cpp
void exp_binaria(mpz_t r, const mpz_t b, const mpz_t e, const mpz_t n) {

	mpz_t expoenteAtual, potenciaAtual;
	mpz_inits(expoenteAtual, potenciaAtual, r, NULL);

	mpz_set(expoenteAtual, e);	// expoenteAtual = e
	mpz_set(potenciaAtual, b);	// potenciaAtual = b
	mpz_set_ui(r, 1);			// r = 1

	while (mpz_cmp_ui(expoenteAtual, 0) > 0) { 	// expoenteAtual > 0
		mpz_t isOdd;
		mpz_init(isOdd);
		mpz_mod_ui(isOdd, expoenteAtual, 2);	// isOdd = expoenteAtual % 2

		if (mpz_cmp_ui(isOdd, 1) == 0) {
			mpz_mul(r, r, potenciaAtual); 	// r = r * r
			mpz_mod(r, r, n);				// r = r % n
		}

		// potenciaAtual = potenciaAtual * potenciaAtual
		mpz_mul(potenciaAtual, potenciaAtual, potenciaAtual);
		// potenciaAtual = potenciaAtual % n
		mpz_mod(potenciaAtual, potenciaAtual, n);
		// expoenteAtual = (int) expoenteAtual / 2
		mpz_fdiv_q_ui(expoenteAtual, expoenteAtual, 2);
	}
}
```
---