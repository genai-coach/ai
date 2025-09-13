# Contributing Guide

Tak fordi du vil bidrage til GenAI Coach!

## Grundprincipper
- Små, isolerede pull requests
- Ét "ansvar" per PR (infra / docs / content / styling adskilt)
- Etik og læsbarhed før "smart" kode

## Workflow
1. Opret et issue (feature / bug) – diskutér scope
2. Vent på kort godkendelse hvis større ændring
3. Opret branch: `feature/...`, `docs/...`, `content/...`, `ui/...`
4. Skriv ændringer + opdater dokumentation
5. Åbn PR med skabelon – udfyld alle relevante sektioner
6. Adresser review-kommentarer
7. Squash & merge (som udgangspunkt)

## Branch Navngivning
- `feature/…`
- `fix/…`
- `docs/…`
- `content/…`
- `ui/…`

## Commit Stil
- Konventionelt præfiks:
  - `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `content:`, `ui:`
- Eksempel: `feat(content): add module 2 evaluation checklist`

## Kodekvalitet (Python)
```bash
black .
flake8 .
mypy .
pytest
```

## Indholdsbidrag (Kurser / Projekter)
- Brug klare læringsmål (LOs)
- Tilføj "Ethical considerations" sektion hvor relevant
- Undgå proprietære datasæt / modeller uden licensinfo
- Front matter (senere hvis vi introducerer metadata)

## AI-Assisteret Indhold
- Må bruges, men:
  - Manuel redigering kræves
  - Ingen hallucinerede referencer
  - Angiv kilde for faktuelle påstande (hvis kritiske)

## Spørgsmål
Opret et issue eller deltag i diskussioner (Discussions kommer senere).