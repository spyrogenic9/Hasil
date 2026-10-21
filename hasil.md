putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python scripts/verify_release.py
PASS | compileall |
PASS | cumulative_unittest_148 | exit=0, tests=148
PASS | cli_smoke_utf-8 | exit=0; markers=True; bytes=55042
PASS | cli_smoke_cp1252 | exit=0; markers=True; bytes=55052
PASS | generalization_cli_smoke | exit=0; markers=True; bytes=21172

Release verification: PASS; 5/5 gates passed.

putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python -m brain_ai.cli --memory generalization_test_state.json
Human-Inspired Cognitive AI v0.12.0 — tanpa LLM
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
Bahasa sederhana: kucing adalah mamalia; jika hujan maka jalan basah; hipotesis tentang cuaca?

KAMU> /generalization-evaluate
{
  "evaluation_id": "GE00001",
  "recorded_at": "2026-10-21T14:19:16.138090+00:00",
  "suite_version": "metamorphic-robustness-v1",
  "seed_case_count": 5,
  "transformations_per_seed": 5,
  "case_count": 25,
  "passed": 25,
  "failed": 0,
  "metamorphic_consistency": 1.0,
  "all_passed": true,
  "context_summary": {
    "direct_relation": {
      "cases": 5,
      "passed": 5,
      "failed": 0,
      "consistency_rate": 1.0
    },
    "transitive_inference": {
      "cases": 5,
      "passed": 5,
      "failed": 0,
      "consistency_rate": 1.0
    },
    "conflict_detection": {
      "cases": 10,
      "passed": 10,
      "failed": 0,
      "consistency_rate": 1.0
    },
    "unsupported_claim": {
      "cases": 5,
      "passed": 5,
      "failed": 0,
      "consistency_rate": 1.0
    }
  },
  "isolation_invariants": {
    "user_facts_unchanged": true,
    "training_ledger_unchanged": true,
    "active_policy_unchanged": true
  },
  "isolation_passed": true,
  "training_ledger_write_count": 0,
  "user_memory_write_count": 0,
  "epistemic_status": "internal_metamorphic_robustness_evaluation_not_external_truth_verification",
  "scope_note": "Evaluasi membandingkan invariants software di bawah transformasi terkontrol. Itu bukan bukti fakta dunia nyata, bukan evaluator eksternal, dan bukan ukuran kecerdasan umum. Seluruh probe berjalan pada memori sementara yang terisolasi.",
  "cases": [
    {
      "case_id": "meta_direct_01::alpha_rename_entities",
      "context": "direct_relation",
      "transformation": "alpha_rename_entities",
      "base_conclusion": "direct_assertion_unverified",
      "transformed_conclusion": "direct_assertion_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_direct_01::reverse_fact_order",
      "context": "direct_relation",
      "transformation": "reverse_fact_order",
      "base_conclusion": "direct_assertion_unverified",
      "transformed_conclusion": "direct_assertion_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_direct_01::duplicate_assertions",
      "context": "direct_relation",
      "transformation": "duplicate_assertions",
      "base_conclusion": "direct_assertion_unverified",
      "transformed_conclusion": "direct_assertion_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_direct_01::add_irrelevant_distractors_and_conflict",
      "context": "direct_relation",
      "transformation": "add_irrelevant_distractors_and_conflict",
      "base_conclusion": "direct_assertion_unverified",
      "transformed_conclusion": "direct_assertion_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_direct_01::add_disconnected_cycle",
      "context": "direct_relation",
      "transformation": "add_disconnected_cycle",
      "base_conclusion": "direct_assertion_unverified",
      "transformed_conclusion": "direct_assertion_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_path_01::alpha_rename_entities",
      "context": "transitive_inference",
      "transformation": "alpha_rename_entities",
      "base_conclusion": "inference_path_unverified",
      "transformed_conclusion": "inference_path_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_path_01::reverse_fact_order",
      "context": "transitive_inference",
      "transformation": "reverse_fact_order",
      "base_conclusion": "inference_path_unverified",
      "transformed_conclusion": "inference_path_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_path_01::duplicate_assertions",
      "context": "transitive_inference",
      "transformation": "duplicate_assertions",
      "base_conclusion": "inference_path_unverified",
      "transformed_conclusion": "inference_path_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_path_01::add_irrelevant_distractors_and_conflict",
      "context": "transitive_inference",
      "transformation": "add_irrelevant_distractors_and_conflict",
      "base_conclusion": "inference_path_unverified",
      "transformed_conclusion": "inference_path_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_path_01::add_disconnected_cycle",
      "context": "transitive_inference",
      "transformation": "add_disconnected_cycle",
      "base_conclusion": "inference_path_unverified",
      "transformed_conclusion": "inference_path_unverified",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_direct_01::alpha_rename_entities",
      "context": "conflict_detection",
      "transformation": "alpha_rename_entities",
      "base_conclusion": "conflicted",
      "transformed_conclusion": "conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_direct_01::reverse_fact_order",
      "context": "conflict_detection",
      "transformation": "reverse_fact_order",
      "base_conclusion": "conflicted",
      "transformed_conclusion": "conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_direct_01::duplicate_assertions",
      "context": "conflict_detection",
      "transformation": "duplicate_assertions",
      "base_conclusion": "conflicted",
      "transformed_conclusion": "conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_direct_01::add_irrelevant_distractors_and_conflict",
      "context": "conflict_detection",
      "transformation": "add_irrelevant_distractors_and_conflict",
      "base_conclusion": "conflicted",
      "transformed_conclusion": "conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_direct_01::add_disconnected_cycle",
      "context": "conflict_detection",
      "transformation": "add_disconnected_cycle",
      "base_conclusion": "conflicted",
      "transformed_conclusion": "conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_path_01::alpha_rename_entities",
      "context": "conflict_detection",
      "transformation": "alpha_rename_entities",
      "base_conclusion": "inference_path_conflicted",
      "transformed_conclusion": "inference_path_conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_path_01::reverse_fact_order",
      "context": "conflict_detection",
      "transformation": "reverse_fact_order",
      "base_conclusion": "inference_path_conflicted",
      "transformed_conclusion": "inference_path_conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_path_01::duplicate_assertions",
      "context": "conflict_detection",
      "transformation": "duplicate_assertions",
      "base_conclusion": "inference_path_conflicted",
      "transformed_conclusion": "inference_path_conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_path_01::add_irrelevant_distractors_and_conflict",
      "context": "conflict_detection",
      "transformation": "add_irrelevant_distractors_and_conflict",
      "base_conclusion": "inference_path_conflicted",
      "transformed_conclusion": "inference_path_conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_conflict_path_01::add_disconnected_cycle",
      "context": "conflict_detection",
      "transformation": "add_disconnected_cycle",
      "base_conclusion": "inference_path_conflicted",
      "transformed_conclusion": "inference_path_conflicted",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_unsupported_01::alpha_rename_entities",
      "context": "unsupported_claim",
      "transformation": "alpha_rename_entities",
      "base_conclusion": "no_support_found_in_stored_memory",
      "transformed_conclusion": "no_support_found_in_stored_memory",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_unsupported_01::reverse_fact_order",
      "context": "unsupported_claim",
      "transformation": "reverse_fact_order",
      "base_conclusion": "no_support_found_in_stored_memory",
      "transformed_conclusion": "no_support_found_in_stored_memory",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_unsupported_01::duplicate_assertions",
      "context": "unsupported_claim",
      "transformation": "duplicate_assertions",
      "base_conclusion": "no_support_found_in_stored_memory",
      "transformed_conclusion": "no_support_found_in_stored_memory",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_unsupported_01::add_irrelevant_distractors_and_conflict",
      "context": "unsupported_claim",
      "transformation": "add_irrelevant_distractors_and_conflict",
      "base_conclusion": "no_support_found_in_stored_memory",
      "transformed_conclusion": "no_support_found_in_stored_memory",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    },
    {
      "case_id": "meta_unsupported_01::add_disconnected_cycle",
      "context": "unsupported_claim",
      "transformation": "add_disconnected_cycle",
      "base_conclusion": "no_support_found_in_stored_memory",
      "transformed_conclusion": "no_support_found_in_stored_memory",
      "checks": {
        "conclusion_invariant": true,
        "strategy_statuses_invariant": true,
        "structural_counts_invariant": true,
        "conflict_not_downgraded": true,
        "focus_policy_known": true
      },
      "passed": true
    }
  ]
}
GENERALIZATION> GE00001 status=PASS consistency=1.000 cases=25/25
CATATAN> metamorphic robustness internal; bukan evaluator eksternal atau verifikasi fakta dunia nyata.
COGNITIVE_UPDATE> siklus=1; WORKSPACE> metamorphic_generalization_lab:metamorphic_generalization_report (0.71), prefrontal_cortex:active_goal (0.61)

KAMU> /generalization-report
{
  "suite_version": "metamorphic-robustness-v1",
  "run_count": 1,
  "latest": {
    "evaluation_id": "GE00001",
    "recorded_at": "2026-10-21T14:19:16.138090+00:00",
    "suite_version": "metamorphic-robustness-v1",
    "seed_case_count": 5,
    "transformations_per_seed": 5,
    "case_count": 25,
    "passed": 25,
    "failed": 0,
    "metamorphic_consistency": 1.0,
    "all_passed": true,
    "isolation_invariants": {
      "user_facts_unchanged": true,
      "training_ledger_unchanged": true,
      "active_policy_unchanged": true
    },
    "isolation_passed": true,
    "epistemic_status": "internal_metamorphic_robustness_evaluation_not_external_truth_verification"
  },
  "recent_runs": [
    {
      "evaluation_id": "GE00001",
      "recorded_at": "2026-10-21T14:19:16.138090+00:00",
      "suite_version": "metamorphic-robustness-v1",
      "seed_case_count": 5,
      "transformations_per_seed": 5,
      "case_count": 25,
      "passed": 25,
      "failed": 0,
      "metamorphic_consistency": 1.0,
      "all_passed": true,
      "isolation_invariants": {
        "user_facts_unchanged": true,
        "training_ledger_unchanged": true,
        "active_policy_unchanged": true
      },
      "isolation_passed": true,
      "epistemic_status": "internal_metamorphic_robustness_evaluation_not_external_truth_verification"
    }
  ],
  "latest_all_passed": true,
  "details_command": "/generalization-evaluate (runs a new isolated evaluation and prints probe-level details)",
  "scope_note": "Metamorphic robustness, not external truth verification."
}

KAMU> /status
{
  "workspace": {
    "cycle": 1,
    "goal": "memahami input dan merespons dengan jujur",
    "arousal": 0.35,
    "learning_rate": 0.2,
    "prediction_error": 0.0,
    "last_action": "evaluate_metamorphic_generalization",
    "working_memory_size": 2,
    "broadcast": [
      {
        "source": "metamorphic_generalization_lab",
        "kind": "metamorphic_generalization_report",
        "content": {
          "evaluation_id": "GE00001",
          "suite_version": "metamorphic-robustness-v1",
          "case_count": 25,
          "passed": 25,
          "failed": 0,
          "all_passed": true,
          "isolation_passed": true
        },
        "confidence": 0.95,
        "novelty": 0.7,
        "urgency": 0.0,
        "goal_relevance": 0.95,
        "evidence": [
          "perubahan atau rencana berasal dari perintah eksplisit pengguna"
        ],
        "score": 0.71
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
  "memory_schema_version": 11,
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
  "generalization_evaluation_runs": 1,
  "latest_generalization_all_passed": true,
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
    "independent_verifier",
    "multi_strategy_reasoner",
    "global_workspace"
  ],
  "llm_used": false
}

KAMU> quit
Memori disimpan. Sampai jumpa.
