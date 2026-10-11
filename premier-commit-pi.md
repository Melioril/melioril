# Premier commit depuis ce PC, via la clé SSH

Fait le 2026-10-11 à 14:24 par pi, pour vérifier que le chemin complet fonctionne :
cle → ssh → GitHub → push. Ce fichier est un artifact de test, supprimable sans consequence :

    git rm premier-commit-pi.md && git commit -m "chore: drop the ssh test artifact" && git push

## Ce qui a ete verifie

- `ssh -T git@github.com` repond `Hi Melioril!`
- cle utilisee : `~/.ssh/id_ed25519_github` (SHA256:MuKisS9+7pHZu04iRGgOUHehEnauaR7qYymUzk2ArUA)
- cles d'hote de github.com installees depuis api.github.com/meta, pas en TOFU aveugle
- identite du commit : `Melioril <340933750+Melioril@users.noreply.github.com>`
  → la forme « noreply », pas l'adresse privee
- `url.git@github.com:.insteadOf https://github.com/` : une URL HTTPS passe desormais par la cle

## Un point a regler cote compte

Le commit initial de ce depot porte `Melioril <melioril@pm.me>` : l'adresse privee est donc
deja publique dans l'historique. A fermer dans *Settings → Emails* : « Keep my email addresses
private » et « Block pushes that contain my private email ».
