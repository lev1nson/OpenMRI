# Security and privacy

OpenMRI is a single-user desktop application. The server binds to
`127.0.0.1` only, has no authentication, and must not be exposed to a network.
Do not put it behind a reverse proxy, a tunnel, or a port forward.

## Medical data

Everything you import stays in your data directory (`.openmri/` by default).
OpenMRI never uploads images, DICOM headers, or patient details anywhere and
makes no network requests while running.

The only scan in the repository is the demo study in `demo/`. It was
anonymised before publication: face removed, headers reduced to geometry. See
[demo/README.md](demo/README.md). The banner and the intro clip are generated
illustrations, and the tests build synthetic DICOM and NIfTI data.

When you report a problem, never attach real scans, DICOM headers, worker
logs with patient names, screenshots that show patient details, or your
`library.sqlite`. Reproduce the problem with the synthetic data from the tests,
or anonymise everything first.

## Reporting a vulnerability

Report security issues privately through **Security → Report a vulnerability**
on the GitHub repository page. Do not open a public issue for them. You will get
an answer within a week.

Anything that would let a web page reach the local server, read files outside
the data directory, or execute code through an imported archive is in scope.
