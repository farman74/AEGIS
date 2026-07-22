# Checklist — OCR

## Objectif

Vérifier qu'un livrable OCR respecte les standards de qualité AEGIS avant validation.

## Quand utiliser

Avant de soumettre un pipeline OCR, une configuration de moteur ou un traitement d'image.

## Prérequis

- Avoir lu `05-Engineering/OCR/RULES.md`

## Procédure

- [ ] Le taux de reconnaissance est mesuré
- [ ] Les scores de confiance sont conservés
- [ ] Les caractères non reconnus sont loggés
- [ ] Le pipeline gère les copies partiellement lisibles
- [ ] La qualité de l'image est vérifiée avant traitement
- [ ] Les résultats sont structurés (JSON avec question et réponse)
- [ ] Les erreurs par ligne et par question sont tracées
- [ ] Le stockage des copies scannées passe par Supabase Storage
- [ ] Les tests de qualité sont définis

## Validation

Tous les points doivent être cochés avant de considérer le livrable comme terminé.

## Références

- `05-Engineering/OCR/RULES.md`
- `04-Agents/OCR/CHECKLIST.md`
