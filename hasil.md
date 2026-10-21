$ python -m brain_ai.cli --version
python -m compileall -q brain_ai tests
python scripts/verify_release.py
cli.py 0.13.1
PASS | version_identity_consistency | VERSION.txt=0.13.1; pyproject=0.13.1; package=0.13.1; cli=cli.py 0.13.1
PASS | compileall |
PASS | cumulative_unittest_167 | exit=0, tests=167
PASS | cli_smoke_utf-8 | exit=0; markers=True; bytes=56585
PASS | cli_smoke_cp1252 | exit=0; markers=True; bytes=56595
PASS | generalization_cli_smoke | exit=0; markers=True; bytes=21377
PASS | crossfit_routing_cli_smoke | exit=0; markers=True; bytes=69828
PASS | holdout_isolation_cli_smoke | exit=0; markers=True; bytes=100636

Release verification: PASS; 8/8 gates passed.
