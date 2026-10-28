# Unofficial fork of Autenticação.gov

This repository is an **unofficial**, independently maintained fork of
[amagovpt/autenticacao.gov](https://github.com/amagovpt/autenticacao.gov),
the Portuguese Citizen Card (Cartão de Cidadão) middleware published by
AMA – Agência para a Modernização Administrativa, I.P.

It is **not produced, endorsed or supported by AMA**. For the official
application, go to <https://www.autenticacao.gov.pt>.

## What is different

- Branch `ubuntu-packaging`: Debian packaging fixed for Ubuntu 24.04. It
  builds an unofficial package named `pteid-mw-jmc`, which can be installed
  alongside the official Flatpak.
- Branch `my-ui`: the application is called "Autenticacao.JoseMCruz", and
  the proprietary Myriad Pro font of the PDF signature seal is replaced by
  SeloSans, a subset of Adobe Source Sans 3 under the SIL OFL 1.1
  (`pteid-mw-pt/_src/eidmw/eidguiV2/fonts/selosans/`).
- Signing with Chave Móvel Digital does not work in this build: it needs
  credentials that AMA does not publish.

## Licence

The project as a whole is distributed under the
[EUPL v1.2](license.txt), as published by AMA. Individual files keep their
own licence headers (EUPL-1.2, LGPL-3.0, GPL-2.0-or-later, MIT); see
`pteid-mw-pt/_src/eidmw/debian/copyright` for a summary. All changes in
this fork are distributed under the same terms.

## Building the Ubuntu 24.04 package

See the build steps in the `ubuntu-packaging` branch history, or:

```bash
cd pteid-mw-pt/_src/eidmw
sudo apt build-dep ./
dpkg-buildpackage -us -uc -b
```

The package is written to `pteid-mw-pt/_src/` (one level up).
