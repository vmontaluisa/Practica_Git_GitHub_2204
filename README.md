# Practica Practica_Git_GitHub_2204


## 1.- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

	Deshacer el último commit y perdiendo los cambios en el working copy) se usa este commando

	git reset --hard HEAD~1



## 2.- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?

Para  deshacerlo despues de git reset --hard HEAD~1, y para  de recuperarlo, siempre y cuando el commit no haya sido eliminado completamente del historial de Git. es  git reset --hard <hash_del_commit> obtenido del git reflog


	victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reflog


	8d4ad62 (HEAD -> styled, main) HEAD@{0}: reset: moving to HEAD~1
	6a1ed6b HEAD@{1}: commit: Estilizar el Git Nuestro
	8d4ad62 (HEAD -> styled, main) HEAD@{2}: checkout: moving from main to styled
	8d4ad62 (HEAD -> styled, main) HEAD@{3}: commit: Añadir el Git Nuestro
	e3a13ee (origin/main, origin/HEAD) HEAD@{4}: clone: from https://github.com/vmontaluisa/Practica_Git_GitHub_2204.git

	victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reset --hard 6a1ed6b



## 3.- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?


		No causo ningun conflicto porque la modificación del archivo git-nuestro.md esta solo en la rama styled

		victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git merge main
		Ya está actualizado.


## 4.- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
		Si causo conflicto porque el archivo git-nuestro.md esta en ambas ramas: styled y htmlify

		victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git merge htmlify
		Auto-fusionando git-nuestro.md
		CONFLICTO (contenido): Conflicto de fusión en git-nuestro.md
		Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.

		Para resolverlo:

				nano git-nuestro.md  # corregir archivo que quede en html
				git add git-nuestro.md
				git commit -m "PAsar HTMLificar del Git Nuestro al styled"
				git merge htmlify


## 5.- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?

		No causo conflicto debidoa  que el archivo git-nuestro.md no estaba  en main como ocurrio antes

				victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git merge styled
				Actualizando 8d4ad62..a535cc7
				Fast-forward
				 git-nuestro.md | 20 ++++++++++----------
				 1 file changed, 10 insertions(+), 10 deletions(-)



## 6.- ¿Qué comando o comandos utilizaste en el paso 25?



		victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git log --graph  --all

				* commit e77dc94ef656e24aad2109ff7de454a530431417 (title)
				| Author: Victor Montaluisa <vmontaluisa@gmail.com>
				| Date:   Sun Sep 15 13:04:34 2024 -0500
				|
				|     Añadir título al  Git Nuestro
				|
				*   commit a535cc71a6f84e3b39729b02f80a8e80ba1b3cbc (HEAD -> main, styled)
				|\  Merge: 6a1ed6b 32ab1de
				| | Author: Victor Montaluisa <vmontaluisa@gmail.com>
				| | Date:   Sun Sep 15 12:56:20 2024 -0500
				| |
				| |     PAsar HTMLificar del Git Nuestro al styled
				| |
				| * commit 32ab1deda756d18b7f1c5eda1578060fcb9c03cb (htmlify)
				| | Author: Victor Montaluisa <vmontaluisa@gmail.com>
				| | Date:   Sun Sep 15 12:45:22 2024 -0500
				| |
				| |     HTMLificar el Git Nuestro
				| |
				* | commit 6a1ed6bffd02c07750e11597ebe6378e05d04523
				|/  Author: Victor Montaluisa <vmontaluisa@gmail.com>
				|   Date:   Sun Sep 15 10:20:27 2024 -0500
				|
				|       Estilizar el Git Nuestro
				|
				* commit 8d4ad628103721a87b083f6723580d7de0feedfc
				| Author: Victor Montaluisa <vmontaluisa@gmail.com>
				| Date:   Sun Sep 15 10:17:51 2024 -0500
				|
				|     Añadir el  Git Nuestro
				|
				* commit e3a13ee538a71f69c72d851ef48568908251e66b (origin/main, origin/HEAD)
				  Author: Victor Montaluisa <vmontaluisa@gmail.com>
				  Date:   Sun Sep 15 03:42:54 2024 -0500

				      Añadir archivo README.md


## 7.- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?

Si fue Fast-forward por que ela rchivo no estaba en main

		victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git merge title
		Actualizando a535cc7..e77dc94
		Fast-forward
		 git-nuestro.md | 7 ++++---
		 1 file changed, 4 insertions(+), 3 deletions(-)


## 8.- ¿Qué comando o comandos utilizaste en el paso 27?

		git reset --merge

					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reflog
					e77dc94 (HEAD -> main, title) HEAD@{0}: merge title: Fast-forward
					a535cc7 (styled) HEAD@{1}: checkout: moving from title to main
					e77dc94 (HEAD -> main, title) HEAD@{2}: commit: Añadir título al Git Nuestro
					a535cc7 (styled) HEAD@{3}: checkout: moving from main to title
					a535cc7 (styled) HEAD@{4}: merge styled: Fast-forward
					8d4ad62 HEAD@{5}: checkout: moving from styled to main
					a535cc7 (styled) HEAD@{6}: commit (merge): PAsar HTMLificar del Git Nuestro al styled
					6a1ed6b HEAD@{7}: reset: moving to HEAD
					6a1ed6b HEAD@{8}: checkout: moving from htmlify to styled
					32ab1de (htmlify) HEAD@{9}: commit: HTMLificar el Git Nuestro
					8d4ad62 HEAD@{10}: checkout: moving from main to htmlify
					8d4ad62 HEAD@{11}: checkout: moving from styled to main
					6a1ed6b HEAD@{12}: reset: moving to 6a1ed6b
					8d4ad62 HEAD@{13}: reset: moving to HEAD~1
					6a1ed6b HEAD@{14}: commit: Estilizar el Git Nuestro
					8d4ad62 HEAD@{15}: checkout: moving from main to styled
					8d4ad62 HEAD@{16}: commit: Añadir el Git Nuestro
					e3a13ee (origin/main, origin/HEAD) HEAD@{17}: clone: from https://github.com/vmontaluisa/Practica_Git_GitHub_2204.git
					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reset --merge

					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reflog
					e77dc94 (HEAD -> main, title) HEAD@{0}: reset: moving to HEAD
					e77dc94 (HEAD -> main, title) HEAD@{1}: merge title: Fast-forward
					a535cc7 (styled) HEAD@{2}: checkout: moving from title to main
					e77dc94 (HEAD -> main, title) HEAD@{3}: commit: Añadir título al Git Nuestro
					a535cc7 (styled) HEAD@{4}: checkout: moving from main to title
					a535cc7 (styled) HEAD@{5}: merge styled: Fast-forward
					8d4ad62 HEAD@{6}: checkout: moving from styled to main
					a535cc7 (styled) HEAD@{7}: commit (merge): PAsar HTMLificar del Git Nuestro al styled
					6a1ed6b HEAD@{8}: reset: moving to HEAD
					6a1ed6b HEAD@{9}: checkout: moving from htmlify to styled
					32ab1de (htmlify) HEAD@{10}: commit: HTMLificar el Git Nuestro
					8d4ad62 HEAD@{11}: checkout: moving from main to htmlify
					8d4ad62 HEAD@{12}: checkout: moving from styled to main
					6a1ed6b HEAD@{13}: reset: moving to 6a1ed6b
					8d4ad62 HEAD@{14}: reset: moving to HEAD~1
					6a1ed6b HEAD@{15}: commit: Estilizar el Git Nuestro
					8d4ad62 HEAD@{16}: checkout: moving from main to styled
					8d4ad62 HEAD@{17}: commit: Añadir el Git Nuestro
					e3a13ee (origin/main, origin/HEAD) HEAD@{18}: clone: from https://github.com/vmontaluisa/Practica_Git_GitHub_2204.git


## 9.- ¿Qué comando o comandos utilizaste en el paso 28?

		git checkout -- git-nuestro.md


## 10.- ¿Qué comando o comandos utilizaste en el paso 29?

			victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git branch -D title
			Eliminada la rama title (era e77dc94).


## 11.- ¿Qué comando o comandos utilizaste en el paso 30?
			victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git merge title


## 12.- ¿Qué comando o comandos usaste en el paso 32?
			git reflog
			git checkout 8d4ad62

					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reflog
					e77dc94 (HEAD -> main) HEAD@{0}: reset: moving to HEAD
					e77dc94 (HEAD -> main) HEAD@{1}: merge title: Fast-forward
					a535cc7 HEAD@{2}: checkout: moving from title to main
					e77dc94 (HEAD -> main) HEAD@{3}: commit: Añadir título al Git Nuestro
					a535cc7 HEAD@{4}: checkout: moving from main to title
					a535cc7 HEAD@{5}: merge styled: Fast-forward
					8d4ad62 HEAD@{6}: checkout: moving from styled to main
					a535cc7 HEAD@{7}: commit (merge): PAsar HTMLificar del Git Nuestro al styled
					6a1ed6b HEAD@{8}: reset: moving to HEAD
					6a1ed6b HEAD@{9}: checkout: moving from htmlify to styled
					32ab1de HEAD@{10}: commit: HTMLificar el Git Nuestro
					8d4ad62 HEAD@{11}: checkout: moving from main to htmlify
					8d4ad62 HEAD@{12}: checkout: moving from styled to main
					6a1ed6b HEAD@{13}: reset: moving to 6a1ed6b
					8d4ad62 HEAD@{14}: reset: moving to HEAD~1
					6a1ed6b HEAD@{15}: commit: Estilizar el Git Nuestro
					8d4ad62 HEAD@{16}: checkout: moving from main to styled
					8d4ad62 HEAD@{17}: commit: Añadir el Git Nuestro
					e3a13ee (origin/main, origin/HEAD) HEAD@{18}: clone: from https://github.com/vmontaluisa/Practica_Git_GitHub_2204.git
					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git checkout 8d4ad62
					Nota: cambiando a '8d4ad62'.

					Te encuentras en estado 'detached HEAD'. Puedes revisar por aquí, hacer
					cambios experimentales y hacer commits, y puedes descartar cualquier
					commit que hayas hecho en este estado sin impactar a tu rama realizando
					otro checkout.

					Si quieres crear una nueva rama para mantener los commits que has creado,
					puedes hacerlo (ahora o después) usando -c con el comando checkout. Ejemplo:

					  git switch -c <nombre-de-nueva-rama>

					O deshacer la operación con:

					  git switch -

					Desactiva este aviso poniendo la variable de config advice.detachedHead en false

					HEAD está ahora en 8d4ad62 Añadir el  Git Nuestro

## 13.- ¿Qué comando o comandos usaste en el punto 33?
				git reflog
				git checkout e77dc94

					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git reflog
					8d4ad62 (HEAD) HEAD@{0}: checkout: moving from main to 8d4ad62
					e77dc94 (main) HEAD@{1}: reset: moving to HEAD
					e77dc94 (main) HEAD@{2}: merge title: Fast-forward
					a535cc7 HEAD@{3}: checkout: moving from title to main
					e77dc94 (main) HEAD@{4}: commit: Añadir título al Git Nuestro
					a535cc7 HEAD@{5}: checkout: moving from main to title
					a535cc7 HEAD@{6}: merge styled: Fast-forward
					8d4ad62 (HEAD) HEAD@{7}: checkout: moving from styled to main
					a535cc7 HEAD@{8}: commit (merge): PAsar HTMLificar del Git Nuestro al styled
					6a1ed6b HEAD@{9}: reset: moving to HEAD
					6a1ed6b HEAD@{10}: checkout: moving from htmlify to styled
					32ab1de HEAD@{11}: commit: HTMLificar el Git Nuestro
					8d4ad62 (HEAD) HEAD@{12}: checkout: moving from main to htmlify
					8d4ad62 (HEAD) HEAD@{13}: checkout: moving from styled to main
					6a1ed6b HEAD@{14}: reset: moving to 6a1ed6b
					8d4ad62 (HEAD) HEAD@{15}: reset: moving to HEAD~1
					6a1ed6b HEAD@{16}: commit: Estilizar el Git Nuestro
					8d4ad62 (HEAD) HEAD@{17}: checkout: moving from main to styled
					8d4ad62 (HEAD) HEAD@{18}: commit: Añadir el Git Nuestro
					e3a13ee (origin/main, origin/HEAD) HEAD@{19}: clone: from https://github.com/vmontaluisa/Practica_Git_GitHub_2204.git
					victormontaluisa@GAMMA Practica_Git_GitHub_2204 % git checkout e77dc94
					La posición previa de HEAD era 8d4ad62 Añadir el  Git Nuestro
					HEAD está ahora en e77dc94 Añadir título al  Git Nuestro
					victormontaluisa@GAMMA Practica_Git_GitHub_2204 %
