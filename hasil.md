putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python -m brain_ai.cli --version
python scripts/verify_release.py
python -m brain_ai.cli --memory counterexample_test_state.json
cli.py 0.14.0
PASS | version_identity_consistency | VERSION.txt=0.14.0; pyproject=0.14.0; package=0.14.0; cli=cli.py 0.14.0
PASS | compileall |
PASS | cumulative_unittest_187 | exit=0, tests=187
PASS | cli_smoke_utf-8 | exit=0; markers=True; bytes=46384
PASS | cli_smoke_cp1252 | exit=0; markers=True; bytes=46394
PASS | generalization_cli_smoke | exit=0; markers=True; bytes=21616
PASS | crossfit_routing_cli_smoke | exit=0; markers=True; bytes=70067
PASS | holdout_isolation_cli_smoke | exit=0; markers=True; bytes=100875
PASS | oracle_counterexample_cli_smoke | exit=0; markers=True; bytes=24744
PASS | oracle_counterexample_250_case_stress | exit=0; markers=True; bytes=106603

Release verification: PASS; 10/10 gates passed.
Human-Inspired Cognitive AI v0.14.0 — tanpa LLM
Perintah: /goal TUJUAN | /status | /facts | /conflicts | /events | /memories | /verify ID_ATAU_KONSEP | /reason SUBJEK | RELASI | OBJEK | /strategies | /feedback POSITIVE|NEGATIVE|NEUTRAL | /quit
Hipotesis: /hypothesis add GRUP | KLAIM | PREDIKSI | /hypotheses [GRUP] | /hypothesis compare GRUP | /hypothesis test ID
Bukti hipotesis: /evidence H0001 support|against|neutral | DESKRIPSI | /evidence-list H0001
Klaim & provenance: /claim add SUBJEK | RELASI | OBJEK; /claim-evidence C00001 supports|refutes|neutral | SOURCE_ID | SOURCE_TYPE | DESKRIPSI
Audit provenance: /claim-report C00001 | /claim-evidence-list C00001 | /claim-audit [C00001]
Catatan pemeriksaan: /claim-check C00001 | PEMERIKSA | METODE | supports|refutes|mixed|inconclusive | ALASAN
Verifier: /verify H0001 untuk ledger hipotesis; /verify C00001 untuk ledger provenance; /verify kucing untuk graf semantik
Strategi: /reason SUBJEK | RELASI | OBJEK; /strategies memisahkan preferensi pengguna dari hasil benchmark
Learning terukur: /learning-benchmark train|holdout|all; /learning-report; /strategy-outcome EPISODE_ID success|partial|failure | EVALUATOR | BASIS
Failure learning: /failure-diagnose EPISODE_ID | EXPECTED_CONCLUSION_STATUS | EVALUATOR_ID | BASIS; /failure-validate LESSON_ID; /failure-report
Mutation lab: /mutation-propose CONTEXT | STRATEGY | RATIONALE; /mutation-report
Generalization lab: /generalization-evaluate; /generalization-report
Routing evaluator: /learning-benchmark train|holdout|all dengan cross-fit; /routing-report
Counterexample lab: /counterexample-search [JUMLAH_KASUS] [SEED]; /counterexample-report
Bahasa sederhana: kucing adalah mamalia; jika hujan maka jalan basah; hipotesis tentang cuaca?

KAMU> /counterexample-search
{
  "evaluation_id": "CXE00001",
  "recorded_at": "2026-10-21T16:22:55.723085+00:00",
  "suite_version": "bounded-oracle-counterexample-v1",
  "seed": 14001,
  "case_count": 40,
  "matched": 40,
  "mismatches": 0,
  "oracle_match_rate": 1.0,
  "all_matched": true,
  "category_summary": {
    "direct": {
      "cases": 8,
      "matched": 8,
      "mismatches": 0
    },
    "transitive": {
      "cases": 8,
      "matched": 8,
      "mismatches": 0
    },
    "target_conflict": {
      "cases": 8,
      "matched": 8,
      "mismatches": 0
    },
    "path_conflict": {
      "cases": 8,
      "matched": 8,
      "mismatches": 0
    },
    "unsupported": {
      "cases": 8,
      "matched": 8,
      "mismatches": 0
    }
  },
  "observed_status_distribution": {
    "direct_assertion_unverified": 8,
    "inference_path_unverified": 6,
    "conflicted": 8,
    "inference_path_conflicted": 8,
    "no_support_found_in_stored_memory": 8,
    "direct_assertion_unverified_with_conflicted_path": 2
  },
  "isolation_invariants": {
    "user_facts_unchanged": true,
    "training_ledger_unchanged": true,
    "caller_outcomes_unchanged": true,
    "active_policy_unchanged": true
  },
  "isolation_passed": true,
  "epistemic_status": "internal_oracle_crosscheck_not_external_truth_verification",
  "scope_note": "The oracle checks only bounded is_a graph semantics over synthetic fixtures. A match is correctness relative to this declared contract, not external truth, general intelligence, or a proof that untested graph shapes are correct.",
  "minimized_counterexamples": []
}
COUNTEREXAMPLE> CXE00001 status=PASS cases=40/40 mismatches=0
CATATAN> oracle graf sintetis internal; bukan verifikasi fakta dunia nyata.
COGNITIVE_UPDATE> siklus=1; WORKSPACE> counterexample_lab:oracle_counterexample_report (0.73), prefrontal_cortex:active_goal (0.61)

KAMU> /counterexample-report
{
  "run_count": 1,
  "latest": {
    "suite_version": "bounded-oracle-counterexample-v1",
    "seed": 14001,
    "case_count": 40,
    "matched": 40,
    "mismatches": 0,
    "oracle_match_rate": 1.0,
    "all_matched": true,
    "category_summary": {
      "direct": {
        "cases": 8,
        "matched": 8,
        "mismatches": 0
      },
      "transitive": {
        "cases": 8,
        "matched": 8,
        "mismatches": 0
      },
      "target_conflict": {
        "cases": 8,
        "matched": 8,
        "mismatches": 0
      },
      "path_conflict": {
        "cases": 8,
        "matched": 8,
        "mismatches": 0
      },
      "unsupported": {
        "cases": 8,
        "matched": 8,
        "mismatches": 0
      }
    },
    "observed_status_distribution": {
      "direct_assertion_unverified": 8,
      "inference_path_unverified": 6,
      "conflicted": 8,
      "inference_path_conflicted": 8,
      "no_support_found_in_stored_memory": 8,
      "direct_assertion_unverified_with_conflicted_path": 2
    },
    "cases": [
      {
        "case_id": "CX0001",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_001_c",
          "is_a",
          "node_001_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0002",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_002_e",
          "is_a",
          "node_002_d"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0003",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_003_d",
          "is_a",
          "node_003_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0004",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_004_d",
          "is_a",
          "node_004_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0005",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_005_f",
          "is_a",
          "node_005_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0006",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_006_b",
          "is_a",
          "node_006_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0007",
        "category": "transitive",
        "fact_count": 2,
        "query": [
          "node_007_b",
          "is_a",
          "node_007_e"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0008",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_008_e",
          "is_a",
          "node_008_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0009",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_009_d",
          "is_a",
          "node_009_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0010",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_010_a",
          "is_a",
          "node_010_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0011",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_011_c",
          "is_a",
          "node_011_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0012",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_012_e",
          "is_a",
          "node_012_f"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0013",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_013_e",
          "is_a",
          "node_013_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0014",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_014_f",
          "is_a",
          "node_014_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0015",
        "category": "unsupported",
        "fact_count": 2,
        "query": [
          "node_015_e",
          "is_a",
          "node_015_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0016",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_016_d",
          "is_a",
          "node_016_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0017",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_017_c",
          "is_a",
          "node_017_d"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0018",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_018_b",
          "is_a",
          "node_018_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0019",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_019_d",
          "is_a",
          "node_019_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0020",
        "category": "unsupported",
        "fact_count": 6,
        "query": [
          "node_020_e",
          "is_a",
          "node_020_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0021",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_021_a",
          "is_a",
          "node_021_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0022",
        "category": "transitive",
        "fact_count": 6,
        "query": [
          "node_022_a",
          "is_a",
          "node_022_c"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0023",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_023_a",
          "is_a",
          "node_023_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0024",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_024_e",
          "is_a",
          "node_024_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0025",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_025_c",
          "is_a",
          "node_025_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0026",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_026_c",
          "is_a",
          "node_026_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0027",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_027_d",
          "is_a",
          "node_027_c"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0028",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_028_d",
          "is_a",
          "node_028_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0029",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_029_d",
          "is_a",
          "node_029_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0030",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_030_a",
          "is_a",
          "node_030_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0031",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_031_c",
          "is_a",
          "node_031_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0032",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_032_a",
          "is_a",
          "node_032_d"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0033",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_033_a",
          "is_a",
          "node_033_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0034",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_034_a",
          "is_a",
          "node_034_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0035",
        "category": "unsupported",
        "fact_count": 2,
        "query": [
          "node_035_e",
          "is_a",
          "node_035_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0036",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_036_d",
          "is_a",
          "node_036_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0037",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_037_f",
          "is_a",
          "node_037_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0038",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_038_b",
          "is_a",
          "node_038_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0039",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_039_a",
          "is_a",
          "node_039_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0040",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_040_a",
          "is_a",
          "node_040_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      }
    ],
    "minimized_counterexamples": [],
    "isolation_invariants": {
      "user_facts_unchanged": true,
      "training_ledger_unchanged": true,
      "caller_outcomes_unchanged": true,
      "active_policy_unchanged": true
    },
    "epistemic_status": "internal_oracle_crosscheck_not_external_truth_verification",
    "scope_note": "The oracle checks only bounded is_a graph semantics over synthetic fixtures. A match is correctness relative to this declared contract, not external truth, general intelligence, or a proof that untested graph shapes are correct.",
    "isolation_passed": true,
    "evaluation_id": "CXE00001",
    "recorded_at": "2026-10-21T16:22:55.723085+00:00"
  },
  "epistemic_note": "The oracle is an internal specification for bounded synthetic graph cases; it is not an external source of truth."
}

KAMU> /status
{
  "workspace": {
    "cycle": 1,
    "goal": "memahami input dan merespons dengan jujur",
    "arousal": 0.35,
    "learning_rate": 0.2,
    "prediction_error": 0.0,
    "last_action": "search_reasoning_counterexamples",
    "working_memory_size": 2,
    "broadcast": [
      {
        "source": "counterexample_lab",
        "kind": "oracle_counterexample_report",
        "content": {
          "evaluation_id": "CXE00001",
          "case_count": 40,
          "matched": 40,
          "mismatches": 0,
          "isolation_passed": true
        },
        "confidence": 0.95,
        "novelty": 0.8,
        "urgency": 0.0,
        "goal_relevance": 0.95,
        "evidence": [
          "perubahan atau rencana berasal dari perintah eksplisit pengguna"
        ],
        "score": 0.73
      },
      {
        "source": "prefrontal_cortex",
        "kind": "active_goal",
        "content": {
          "goal": "memahami input dan merespons dengan jujur",
          "task_kind": "structured_command"
        },
        "confidence": 0.9,
        "novelty": 0.1,
        "urgency": 0.1,
        "goal_relevance": 1.0,
        "evidence": [
          "tujuan aktif sistem"
        ],
        "score": 0.615
      }
    ]
  },
  "cognitive_cycles_this_run": 1,
  "cognitive_cycles_total": 1,
  "episodic_memories": 1,
  "semantic_relations": 0,
  "hypotheses": 0,
  "hypothesis_evidence_records": 0,
  "provenance_claims": 0,
  "provenance_evidence_records": 0,
  "provenance_external_checks": 0,
  "memory_schema_version": 13,
  "feedback_count": 0,
  "average_reward": null,
  "action_values": {},
  "strategy_learning": {},
  "strategy_applicability_learning": {},
  "strategy_benchmark_training_trials": 0,
  "strategy_declared_outcomes": 0,
  "failure_diagnoses": 0,
  "reusable_strategy_lessons": 0,
  "strategy_mutations": 0,
  "active_strategy_policy_overrides": {},
  "generalization_evaluation_runs": 0,
  "routing_evaluation_runs": 0,
  "counterexample_evaluation_runs": 1,
  "latest_counterexample_oracle_match_rate": 1.0,
  "latest_routing_accuracy": null,
  "latest_generalization_all_passed": null,
  "unresolved_contradictions": [],
  "event_count_this_run": 9,
  "needs": {
    "energy": 1.0,
    "novelty_seeking": 0.25,
    "social_interaction": 0.3
  },
  "components": [
    "thalamus_attention",
    "working_memory",
    "hippocampus",
    "amygdala",
    "basal_ganglia",
    "prefrontal_cortex",
    "cerebellum",
    "hypothalamus_sleep",
    "neuromodulator",
    "default_mode_network",
    "language_area",
    "perception",
    "world_model",
    "hypothesis_system",
    "claim_evidence_provenance_ledger",
    "outcome_based_strategy_applicability_learning",
    "structured_failure_diagnosis_and_reusable_lesson_candidates",
    "holdout_validated_strategy_mutation_lab",
    "metamorphic_generalization_lab",
    "cross_fitted_strategy_routing_evaluator",
    "oracle_backed_counterexample_search_and_minimization",
    "independent_verifier",
    "multi_strategy_reasoner",
    "global_workspace"
  ],
  "llm_used": false
}

KAMU> /counterexample-search 250 8675309
{
  "evaluation_id": "CXE00002",
  "recorded_at": "2026-10-21T16:23:13.882438+00:00",
  "suite_version": "bounded-oracle-counterexample-v1",
  "seed": 8675309,
  "case_count": 250,
  "matched": 250,
  "mismatches": 0,
  "oracle_match_rate": 1.0,
  "all_matched": true,
  "category_summary": {
    "direct": {
      "cases": 50,
      "matched": 50,
      "mismatches": 0
    },
    "transitive": {
      "cases": 50,
      "matched": 50,
      "mismatches": 0
    },
    "target_conflict": {
      "cases": 50,
      "matched": 50,
      "mismatches": 0
    },
    "path_conflict": {
      "cases": 50,
      "matched": 50,
      "mismatches": 0
    },
    "unsupported": {
      "cases": 50,
      "matched": 50,
      "mismatches": 0
    }
  },
  "observed_status_distribution": {
    "direct_assertion_unverified": 47,
    "conflicted": 50,
    "inference_path_conflicted": 67,
    "no_support_found_in_stored_memory": 50,
    "direct_assertion_unverified_with_conflicted_path": 17,
    "inference_path_unverified": 19
  },
  "isolation_invariants": {
    "user_facts_unchanged": true,
    "training_ledger_unchanged": true,
    "caller_outcomes_unchanged": true,
    "active_policy_unchanged": true
  },
  "isolation_passed": true,
  "epistemic_status": "internal_oracle_crosscheck_not_external_truth_verification",
  "scope_note": "The oracle checks only bounded is_a graph semantics over synthetic fixtures. A match is correctness relative to this declared contract, not external truth, general intelligence, or a proof that untested graph shapes are correct.",
  "minimized_counterexamples": []
}
COUNTEREXAMPLE> CXE00002 status=PASS cases=250/250 mismatches=0
CATATAN> oracle graf sintetis internal; bukan verifikasi fakta dunia nyata.
COGNITIVE_UPDATE> siklus=2; WORKSPACE> counterexample_lab:oracle_counterexample_report (0.73), prefrontal_cortex:active_goal (0.61)

KAMU> /counterexample-report
{
  "run_count": 2,
  "latest": {
    "suite_version": "bounded-oracle-counterexample-v1",
    "seed": 8675309,
    "case_count": 250,
    "matched": 250,
    "mismatches": 0,
    "oracle_match_rate": 1.0,
    "all_matched": true,
    "category_summary": {
      "direct": {
        "cases": 50,
        "matched": 50,
        "mismatches": 0
      },
      "transitive": {
        "cases": 50,
        "matched": 50,
        "mismatches": 0
      },
      "target_conflict": {
        "cases": 50,
        "matched": 50,
        "mismatches": 0
      },
      "path_conflict": {
        "cases": 50,
        "matched": 50,
        "mismatches": 0
      },
      "unsupported": {
        "cases": 50,
        "matched": 50,
        "mismatches": 0
      }
    },
    "observed_status_distribution": {
      "direct_assertion_unverified": 47,
      "conflicted": 50,
      "inference_path_conflicted": 67,
      "no_support_found_in_stored_memory": 50,
      "direct_assertion_unverified_with_conflicted_path": 17,
      "inference_path_unverified": 19
    },
    "cases": [
      {
        "case_id": "CX0001",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_001_c",
          "is_a",
          "node_001_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0002",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_002_e",
          "is_a",
          "node_002_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0003",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_003_d",
          "is_a",
          "node_003_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0004",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_004_c",
          "is_a",
          "node_004_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0005",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_005_a",
          "is_a",
          "node_005_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0006",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_006_d",
          "is_a",
          "node_006_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0007",
        "category": "transitive",
        "fact_count": 7,
        "query": [
          "node_007_e",
          "is_a",
          "node_007_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0008",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_008_f",
          "is_a",
          "node_008_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0009",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_009_b",
          "is_a",
          "node_009_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0010",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_010_b",
          "is_a",
          "node_010_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0011",
        "category": "direct",
        "fact_count": 6,
        "query": [
          "node_011_e",
          "is_a",
          "node_011_d"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0012",
        "category": "transitive",
        "fact_count": 6,
        "query": [
          "node_012_f",
          "is_a",
          "node_012_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0013",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_013_d",
          "is_a",
          "node_013_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0014",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_014_b",
          "is_a",
          "node_014_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0015",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_015_a",
          "is_a",
          "node_015_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0016",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_016_f",
          "is_a",
          "node_016_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0017",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_017_e",
          "is_a",
          "node_017_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0018",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_018_a",
          "is_a",
          "node_018_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0019",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_019_f",
          "is_a",
          "node_019_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0020",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_020_f",
          "is_a",
          "node_020_e"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0021",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_021_a",
          "is_a",
          "node_021_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0022",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_022_a",
          "is_a",
          "node_022_e"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0023",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_023_f",
          "is_a",
          "node_023_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0024",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_024_a",
          "is_a",
          "node_024_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0025",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_025_b",
          "is_a",
          "node_025_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0026",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_026_a",
          "is_a",
          "node_026_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0027",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_027_f",
          "is_a",
          "node_027_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0028",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_028_f",
          "is_a",
          "node_028_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0029",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_029_b",
          "is_a",
          "node_029_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0030",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_030_e",
          "is_a",
          "node_030_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0031",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_031_a",
          "is_a",
          "node_031_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0032",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_032_a",
          "is_a",
          "node_032_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0033",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_033_f",
          "is_a",
          "node_033_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0034",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_034_d",
          "is_a",
          "node_034_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0035",
        "category": "unsupported",
        "fact_count": 6,
        "query": [
          "node_035_f",
          "is_a",
          "node_035_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0036",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_036_a",
          "is_a",
          "node_036_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0037",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_037_e",
          "is_a",
          "node_037_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0038",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_038_b",
          "is_a",
          "node_038_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0039",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_039_e",
          "is_a",
          "node_039_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0040",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_040_e",
          "is_a",
          "node_040_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0041",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_041_a",
          "is_a",
          "node_041_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0042",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_042_f",
          "is_a",
          "node_042_d"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0043",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_043_c",
          "is_a",
          "node_043_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0044",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_044_b",
          "is_a",
          "node_044_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0045",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_045_d",
          "is_a",
          "node_045_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0046",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_046_d",
          "is_a",
          "node_046_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0047",
        "category": "transitive",
        "fact_count": 6,
        "query": [
          "node_047_f",
          "is_a",
          "node_047_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0048",
        "category": "target_conflict",
        "fact_count": 1,
        "query": [
          "node_048_d",
          "is_a",
          "node_048_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0049",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_049_b",
          "is_a",
          "node_049_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0050",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_050_a",
          "is_a",
          "node_050_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0051",
        "category": "direct",
        "fact_count": 7,
        "query": [
          "node_051_a",
          "is_a",
          "node_051_e"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0052",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_052_f",
          "is_a",
          "node_052_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0053",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_053_e",
          "is_a",
          "node_053_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0054",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_054_b",
          "is_a",
          "node_054_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0055",
        "category": "unsupported",
        "fact_count": 6,
        "query": [
          "node_055_e",
          "is_a",
          "node_055_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0056",
        "category": "direct",
        "fact_count": 3,
        "query": [
          "node_056_b",
          "is_a",
          "node_056_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0057",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_057_c",
          "is_a",
          "node_057_e"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0058",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_058_d",
          "is_a",
          "node_058_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0059",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_059_f",
          "is_a",
          "node_059_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0060",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_060_b",
          "is_a",
          "node_060_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0061",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_061_e",
          "is_a",
          "node_061_c"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0062",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_062_c",
          "is_a",
          "node_062_b"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0063",
        "category": "target_conflict",
        "fact_count": 1,
        "query": [
          "node_063_d",
          "is_a",
          "node_063_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0064",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_064_c",
          "is_a",
          "node_064_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0065",
        "category": "unsupported",
        "fact_count": 2,
        "query": [
          "node_065_c",
          "is_a",
          "node_065_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0066",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_066_f",
          "is_a",
          "node_066_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0067",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_067_a",
          "is_a",
          "node_067_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0068",
        "category": "target_conflict",
        "fact_count": 6,
        "query": [
          "node_068_b",
          "is_a",
          "node_068_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0069",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_069_a",
          "is_a",
          "node_069_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0070",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_070_d",
          "is_a",
          "node_070_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0071",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_071_c",
          "is_a",
          "node_071_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0072",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_072_c",
          "is_a",
          "node_072_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0073",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_073_e",
          "is_a",
          "node_073_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0074",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_074_c",
          "is_a",
          "node_074_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0075",
        "category": "unsupported",
        "fact_count": 6,
        "query": [
          "node_075_a",
          "is_a",
          "node_075_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0076",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_076_f",
          "is_a",
          "node_076_a"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0077",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_077_c",
          "is_a",
          "node_077_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0078",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_078_c",
          "is_a",
          "node_078_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0079",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_079_d",
          "is_a",
          "node_079_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0080",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_080_e",
          "is_a",
          "node_080_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0081",
        "category": "direct",
        "fact_count": 6,
        "query": [
          "node_081_b",
          "is_a",
          "node_081_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0082",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_082_b",
          "is_a",
          "node_082_c"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0083",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_083_c",
          "is_a",
          "node_083_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0084",
        "category": "path_conflict",
        "fact_count": 7,
        "query": [
          "node_084_e",
          "is_a",
          "node_084_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0085",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_085_a",
          "is_a",
          "node_085_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0086",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_086_c",
          "is_a",
          "node_086_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0087",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_087_a",
          "is_a",
          "node_087_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0088",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_088_b",
          "is_a",
          "node_088_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0089",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_089_f",
          "is_a",
          "node_089_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0090",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_090_e",
          "is_a",
          "node_090_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0091",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_091_d",
          "is_a",
          "node_091_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0092",
        "category": "transitive",
        "fact_count": 2,
        "query": [
          "node_092_a",
          "is_a",
          "node_092_d"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0093",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_093_d",
          "is_a",
          "node_093_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0094",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_094_a",
          "is_a",
          "node_094_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0095",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_095_b",
          "is_a",
          "node_095_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0096",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_096_b",
          "is_a",
          "node_096_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0097",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_097_e",
          "is_a",
          "node_097_f"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0098",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_098_b",
          "is_a",
          "node_098_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0099",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_099_c",
          "is_a",
          "node_099_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0100",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_100_b",
          "is_a",
          "node_100_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0101",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_101_d",
          "is_a",
          "node_101_c"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0102",
        "category": "transitive",
        "fact_count": 6,
        "query": [
          "node_102_f",
          "is_a",
          "node_102_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0103",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_103_e",
          "is_a",
          "node_103_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0104",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_104_c",
          "is_a",
          "node_104_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0105",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_105_e",
          "is_a",
          "node_105_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0106",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_106_e",
          "is_a",
          "node_106_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0107",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_107_d",
          "is_a",
          "node_107_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0108",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_108_d",
          "is_a",
          "node_108_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0109",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_109_e",
          "is_a",
          "node_109_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0110",
        "category": "unsupported",
        "fact_count": 8,
        "query": [
          "node_110_e",
          "is_a",
          "node_110_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0111",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_111_d",
          "is_a",
          "node_111_e"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0112",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_112_b",
          "is_a",
          "node_112_d"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0113",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_113_a",
          "is_a",
          "node_113_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0114",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_114_e",
          "is_a",
          "node_114_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0115",
        "category": "unsupported",
        "fact_count": 2,
        "query": [
          "node_115_f",
          "is_a",
          "node_115_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0116",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_116_a",
          "is_a",
          "node_116_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0117",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_117_b",
          "is_a",
          "node_117_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0118",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_118_f",
          "is_a",
          "node_118_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0119",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_119_f",
          "is_a",
          "node_119_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0120",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_120_a",
          "is_a",
          "node_120_e"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0121",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_121_d",
          "is_a",
          "node_121_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0122",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_122_d",
          "is_a",
          "node_122_b"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0123",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_123_a",
          "is_a",
          "node_123_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0124",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_124_f",
          "is_a",
          "node_124_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0125",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_125_d",
          "is_a",
          "node_125_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0126",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_126_a",
          "is_a",
          "node_126_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0127",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_127_b",
          "is_a",
          "node_127_c"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0128",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_128_a",
          "is_a",
          "node_128_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0129",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_129_e",
          "is_a",
          "node_129_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0130",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_130_f",
          "is_a",
          "node_130_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0131",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_131_e",
          "is_a",
          "node_131_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0132",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_132_f",
          "is_a",
          "node_132_c"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0133",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_133_f",
          "is_a",
          "node_133_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0134",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_134_d",
          "is_a",
          "node_134_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0135",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_135_f",
          "is_a",
          "node_135_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0136",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_136_d",
          "is_a",
          "node_136_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0137",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_137_d",
          "is_a",
          "node_137_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0138",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_138_a",
          "is_a",
          "node_138_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0139",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_139_c",
          "is_a",
          "node_139_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0140",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_140_f",
          "is_a",
          "node_140_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0141",
        "category": "direct",
        "fact_count": 3,
        "query": [
          "node_141_c",
          "is_a",
          "node_141_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0142",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_142_c",
          "is_a",
          "node_142_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0143",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_143_e",
          "is_a",
          "node_143_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0144",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_144_a",
          "is_a",
          "node_144_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0145",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_145_b",
          "is_a",
          "node_145_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0146",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_146_e",
          "is_a",
          "node_146_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0147",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_147_c",
          "is_a",
          "node_147_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0148",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_148_c",
          "is_a",
          "node_148_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0149",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_149_d",
          "is_a",
          "node_149_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0150",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_150_b",
          "is_a",
          "node_150_e"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0151",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_151_b",
          "is_a",
          "node_151_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0152",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_152_a",
          "is_a",
          "node_152_c"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0153",
        "category": "target_conflict",
        "fact_count": 6,
        "query": [
          "node_153_c",
          "is_a",
          "node_153_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0154",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_154_a",
          "is_a",
          "node_154_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0155",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_155_d",
          "is_a",
          "node_155_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0156",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_156_c",
          "is_a",
          "node_156_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0157",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_157_b",
          "is_a",
          "node_157_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0158",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_158_e",
          "is_a",
          "node_158_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0159",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_159_e",
          "is_a",
          "node_159_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0160",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_160_c",
          "is_a",
          "node_160_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0161",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_161_b",
          "is_a",
          "node_161_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0162",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_162_e",
          "is_a",
          "node_162_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0163",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_163_b",
          "is_a",
          "node_163_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0164",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_164_e",
          "is_a",
          "node_164_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0165",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_165_c",
          "is_a",
          "node_165_e"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0166",
        "category": "direct",
        "fact_count": 6,
        "query": [
          "node_166_e",
          "is_a",
          "node_166_c"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0167",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_167_c",
          "is_a",
          "node_167_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0168",
        "category": "target_conflict",
        "fact_count": 7,
        "query": [
          "node_168_e",
          "is_a",
          "node_168_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0169",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_169_d",
          "is_a",
          "node_169_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0170",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_170_b",
          "is_a",
          "node_170_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0171",
        "category": "direct",
        "fact_count": 3,
        "query": [
          "node_171_c",
          "is_a",
          "node_171_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0172",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_172_f",
          "is_a",
          "node_172_e"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0173",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_173_e",
          "is_a",
          "node_173_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0174",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_174_c",
          "is_a",
          "node_174_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0175",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_175_b",
          "is_a",
          "node_175_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0176",
        "category": "direct",
        "fact_count": 3,
        "query": [
          "node_176_e",
          "is_a",
          "node_176_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0177",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_177_d",
          "is_a",
          "node_177_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0178",
        "category": "target_conflict",
        "fact_count": 1,
        "query": [
          "node_178_e",
          "is_a",
          "node_178_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0179",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_179_f",
          "is_a",
          "node_179_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0180",
        "category": "unsupported",
        "fact_count": 2,
        "query": [
          "node_180_c",
          "is_a",
          "node_180_e"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0181",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_181_d",
          "is_a",
          "node_181_e"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0182",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_182_c",
          "is_a",
          "node_182_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0183",
        "category": "target_conflict",
        "fact_count": 1,
        "query": [
          "node_183_b",
          "is_a",
          "node_183_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0184",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_184_b",
          "is_a",
          "node_184_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0185",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_185_a",
          "is_a",
          "node_185_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0186",
        "category": "direct",
        "fact_count": 3,
        "query": [
          "node_186_b",
          "is_a",
          "node_186_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0187",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_187_e",
          "is_a",
          "node_187_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0188",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_188_d",
          "is_a",
          "node_188_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0189",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_189_f",
          "is_a",
          "node_189_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0190",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_190_c",
          "is_a",
          "node_190_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0191",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_191_e",
          "is_a",
          "node_191_a"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0192",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_192_d",
          "is_a",
          "node_192_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0193",
        "category": "target_conflict",
        "fact_count": 6,
        "query": [
          "node_193_c",
          "is_a",
          "node_193_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0194",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_194_e",
          "is_a",
          "node_194_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0195",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_195_c",
          "is_a",
          "node_195_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0196",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_196_a",
          "is_a",
          "node_196_b"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0197",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_197_d",
          "is_a",
          "node_197_f"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0198",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_198_e",
          "is_a",
          "node_198_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0199",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_199_e",
          "is_a",
          "node_199_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0200",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_200_e",
          "is_a",
          "node_200_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0201",
        "category": "direct",
        "fact_count": 2,
        "query": [
          "node_201_f",
          "is_a",
          "node_201_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0202",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_202_e",
          "is_a",
          "node_202_c"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0203",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_203_d",
          "is_a",
          "node_203_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0204",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_204_e",
          "is_a",
          "node_204_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0205",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_205_e",
          "is_a",
          "node_205_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0206",
        "category": "direct",
        "fact_count": 4,
        "query": [
          "node_206_f",
          "is_a",
          "node_206_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0207",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_207_b",
          "is_a",
          "node_207_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0208",
        "category": "target_conflict",
        "fact_count": 1,
        "query": [
          "node_208_a",
          "is_a",
          "node_208_e"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0209",
        "category": "path_conflict",
        "fact_count": 4,
        "query": [
          "node_209_e",
          "is_a",
          "node_209_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0210",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_210_b",
          "is_a",
          "node_210_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0211",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_211_f",
          "is_a",
          "node_211_a"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0212",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_212_a",
          "is_a",
          "node_212_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0213",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_213_c",
          "is_a",
          "node_213_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0214",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_214_c",
          "is_a",
          "node_214_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0215",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_215_f",
          "is_a",
          "node_215_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0216",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_216_f",
          "is_a",
          "node_216_d"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0217",
        "category": "transitive",
        "fact_count": 3,
        "query": [
          "node_217_c",
          "is_a",
          "node_217_e"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0218",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_218_e",
          "is_a",
          "node_218_f"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0219",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_219_b",
          "is_a",
          "node_219_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0220",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_220_c",
          "is_a",
          "node_220_f"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0221",
        "category": "direct",
        "fact_count": 7,
        "query": [
          "node_221_e",
          "is_a",
          "node_221_b"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0222",
        "category": "transitive",
        "fact_count": 2,
        "query": [
          "node_222_d",
          "is_a",
          "node_222_a"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0223",
        "category": "target_conflict",
        "fact_count": 1,
        "query": [
          "node_223_e",
          "is_a",
          "node_223_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0224",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_224_d",
          "is_a",
          "node_224_c"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0225",
        "category": "unsupported",
        "fact_count": 5,
        "query": [
          "node_225_c",
          "is_a",
          "node_225_a"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0226",
        "category": "direct",
        "fact_count": 1,
        "query": [
          "node_226_b",
          "is_a",
          "node_226_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0227",
        "category": "transitive",
        "fact_count": 6,
        "query": [
          "node_227_c",
          "is_a",
          "node_227_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0228",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_228_e",
          "is_a",
          "node_228_c"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0229",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_229_d",
          "is_a",
          "node_229_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0230",
        "category": "unsupported",
        "fact_count": 4,
        "query": [
          "node_230_a",
          "is_a",
          "node_230_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0231",
        "category": "direct",
        "fact_count": 6,
        "query": [
          "node_231_a",
          "is_a",
          "node_231_d"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0232",
        "category": "transitive",
        "fact_count": 5,
        "query": [
          "node_232_a",
          "is_a",
          "node_232_d"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0233",
        "category": "target_conflict",
        "fact_count": 4,
        "query": [
          "node_233_f",
          "is_a",
          "node_233_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0234",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_234_d",
          "is_a",
          "node_234_b"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0235",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_235_f",
          "is_a",
          "node_235_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0236",
        "category": "direct",
        "fact_count": 5,
        "query": [
          "node_236_f",
          "is_a",
          "node_236_b"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0237",
        "category": "transitive",
        "fact_count": 2,
        "query": [
          "node_237_b",
          "is_a",
          "node_237_c"
        ],
        "expected_status": "inference_path_unverified",
        "observed_status": "inference_path_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0238",
        "category": "target_conflict",
        "fact_count": 2,
        "query": [
          "node_238_f",
          "is_a",
          "node_238_b"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0239",
        "category": "path_conflict",
        "fact_count": 3,
        "query": [
          "node_239_b",
          "is_a",
          "node_239_e"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0240",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_240_c",
          "is_a",
          "node_240_d"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0241",
        "category": "direct",
        "fact_count": 3,
        "query": [
          "node_241_c",
          "is_a",
          "node_241_f"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0242",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_242_b",
          "is_a",
          "node_242_c"
        ],
        "expected_status": "direct_assertion_unverified",
        "observed_status": "direct_assertion_unverified",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0243",
        "category": "target_conflict",
        "fact_count": 3,
        "query": [
          "node_243_e",
          "is_a",
          "node_243_d"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0244",
        "category": "path_conflict",
        "fact_count": 5,
        "query": [
          "node_244_e",
          "is_a",
          "node_244_a"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0245",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_245_f",
          "is_a",
          "node_245_b"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      },
      {
        "case_id": "CX0246",
        "category": "direct",
        "fact_count": 6,
        "query": [
          "node_246_e",
          "is_a",
          "node_246_c"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0247",
        "category": "transitive",
        "fact_count": 4,
        "query": [
          "node_247_b",
          "is_a",
          "node_247_e"
        ],
        "expected_status": "direct_assertion_unverified_with_conflicted_path",
        "observed_status": "direct_assertion_unverified_with_conflicted_path",
        "oracle_path_count": 2,
        "production_path_count": 2,
        "match": true
      },
      {
        "case_id": "CX0248",
        "category": "target_conflict",
        "fact_count": 5,
        "query": [
          "node_248_e",
          "is_a",
          "node_248_a"
        ],
        "expected_status": "conflicted",
        "observed_status": "conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0249",
        "category": "path_conflict",
        "fact_count": 6,
        "query": [
          "node_249_c",
          "is_a",
          "node_249_f"
        ],
        "expected_status": "inference_path_conflicted",
        "observed_status": "inference_path_conflicted",
        "oracle_path_count": 1,
        "production_path_count": 1,
        "match": true
      },
      {
        "case_id": "CX0250",
        "category": "unsupported",
        "fact_count": 3,
        "query": [
          "node_250_d",
          "is_a",
          "node_250_c"
        ],
        "expected_status": "no_support_found_in_stored_memory",
        "observed_status": "no_support_found_in_stored_memory",
        "oracle_path_count": 0,
        "production_path_count": 0,
        "match": true
      }
    ],
    "minimized_counterexamples": [],
    "isolation_invariants": {
      "user_facts_unchanged": true,
      "training_ledger_unchanged": true,
      "caller_outcomes_unchanged": true,
      "active_policy_unchanged": true
    },
    "epistemic_status": "internal_oracle_crosscheck_not_external_truth_verification",
    "scope_note": "The oracle checks only bounded is_a graph semantics over synthetic fixtures. A match is correctness relative to this declared contract, not external truth, general intelligence, or a proof that untested graph shapes are correct.",
    "isolation_passed": true,
    "evaluation_id": "CXE00002",
    "recorded_at": "2026-10-21T16:23:13.882438+00:00"
  },
  "epistemic_note": "The oracle is an internal specification for bounded synthetic graph cases; it is not an external source of truth."
}

KAMU> quit
Memori disimpan. Sampai jumpa.
