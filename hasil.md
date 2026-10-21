putra@L MINGW64 ~/Downloads/Video/BRAIN
$  python -m compileall -q .
python -m unittest discover -s tests -v
test_empty_input_rejected (test_brain.CognitiveBrainTests.test_empty_input_rejected) ... ok
test_exit_aliases_are_recognized (test_brain.CognitiveBrainTests.test_exit_aliases_are_recognized) ... ok
test_feedback_changes_learning_parameters (test_brain.CognitiveBrainTests.test_feedback_changes_learning_parameters) ... ok
test_learns_simple_relation_and_retrieves_it (test_brain.CognitiveBrainTests.test_learns_simple_relation_and_retrieves_it) ... ok
test_memory_persists (test_brain.CognitiveBrainTests.test_memory_persists) ... ok
test_repeated_assertion_does_not_make_fact_verified (test_brain.CognitiveBrainTests.test_repeated_assertion_does_not_make_fact_verified) ... ok
test_selected_action_matches_response_route (test_brain.CognitiveBrainTests.test_selected_action_matches_response_route) ... ok
test_transitive_is_a_inference_is_labeled_unverified (test_brain.CognitiveBrainTests.test_transitive_is_a_inference_is_labeled_unverified) ... ok
test_v01_relation_migrates_from_source_text (test_brain.CognitiveBrainTests.test_v01_relation_migrates_from_source_text) ... ok
test_workspace_broadcast_is_bounded (test_brain.CognitiveBrainTests.test_workspace_broadcast_is_bounded) ... ok
test_audit_does_not_claim_truth_verification (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_audit_does_not_claim_truth_verification) ... ok
test_claim_context_partitions_claim_identity (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_claim_context_partitions_claim_identity) ... ok
test_conflict_is_preserved (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_conflict_is_preserved) ... ok
test_exact_duplicate_is_ignored (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_exact_duplicate_is_ignored) ... ok
test_external_check_cannot_reference_another_claims_evidence (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_external_check_cannot_reference_another_claims_evidence) ... ok
test_external_check_does_not_delete_conflict (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_external_check_does_not_delete_conflict) ... ok
test_invalid_ledger_payload_is_rejected_without_reset (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_invalid_ledger_payload_is_rejected_without_reset) ... ok
test_invalid_references_are_rejected (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_invalid_references_are_rejected) ... ok
test_invalid_stance_and_blank_source_are_rejected (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_invalid_stance_and_blank_source_are_rejected) ... ok
test_neutral_evidence_does_not_become_support (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_neutral_evidence_does_not_become_support) ... ok
test_no_evidence_is_not_a_truth_claim (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_no_evidence_is_not_a_truth_claim) ... ok
test_persistence_after_reopen (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_persistence_after_reopen) ... ok
test_repetition_from_same_source_is_not_independent (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_repetition_from_same_source_is_not_independent) ... ok
test_shared_independent_group_counts_as_one_declared_source_group (test_evidence_ledger.IntegratedEvidenceLedgerTests.test_shared_independent_group_counts_as_one_declared_source_group) ... ok
test_cli_failure_diagnosis_is_persisted_and_reported_after_restart (test_failure_learning_v0101.FailureLearningCLITests.test_cli_failure_diagnosis_is_persisted_and_reported_after_restart) ... ok
test_cli_supports_cp1252_and_shows_reused_failure_lesson (test_failure_learning_v0101.FailureLearningCLITests.test_cli_supports_cp1252_and_shows_reused_failure_lesson) ... ok
test_all_supported_statuses_are_declared_and_no_mismatch_is_deterministic (test_failure_learning_v0101.FailureLearningCoreTests.test_all_supported_statuses_are_declared_and_no_mismatch_is_deterministic) ... ok
test_diagnosis_and_lessons_persist_after_restart (test_failure_learning_v0101.FailureLearningCoreTests.test_diagnosis_and_lessons_persist_after_restart) ... ok
test_diagnosis_identifies_missed_conflict_without_modifying_facts_or_verdict (test_failure_learning_v0101.FailureLearningCoreTests.test_diagnosis_identifies_missed_conflict_without_modifying_facts_or_verdict) ... ok
test_failure_diagnosis_rejects_duplicate_episode (test_failure_learning_v0101.FailureLearningCoreTests.test_failure_diagnosis_rejects_duplicate_episode) ... ok
test_failure_diagnosis_rejects_non_reasoning_episode (test_failure_learning_v0101.FailureLearningCoreTests.test_failure_diagnosis_rejects_non_reasoning_episode) ... ok
test_failure_lesson_reaches_repeated_candidate_only_after_distinct_episode_and_evaluator_ids (test_failure_learning_v0101.FailureLearningCoreTests.test_failure_lesson_reaches_repeated_candidate_only_after_distinct_episode_and_evaluator_ids) ... ok
test_failure_lessons_are_reused_as_advisory_items_not_fact_or_verdict_overrides (test_failure_learning_v0101.FailureLearningCoreTests.test_failure_lessons_are_reused_as_advisory_items_not_fact_or_verdict_overrides) ... ok
test_holdout_validation_does_not_train_or_activate_lesson (test_failure_learning_v0101.FailureLearningCoreTests.test_holdout_validation_does_not_train_or_activate_lesson) ... ok
test_holdout_validation_rejects_provisional_lesson (test_failure_learning_v0101.FailureLearningCoreTests.test_holdout_validation_rejects_provisional_lesson) ... ok
test_invalid_expected_status_is_rejected (test_failure_learning_v0101.FailureLearningCoreTests.test_invalid_expected_status_is_rejected) ... ok
test_matching_expected_status_does_not_generate_failure_lesson (test_failure_learning_v0101.FailureLearningCoreTests.test_matching_expected_status_does_not_generate_failure_lesson) ... ok
test_same_evaluator_on_separate_episodes_does_not_promote_lesson (test_failure_learning_v0101.FailureLearningCoreTests.test_same_evaluator_on_separate_episodes_does_not_promote_lesson) ... ok
test_schema_v8_state_migrates_to_current_without_losing_fields (test_failure_learning_v0101.FailureLearningCoreTests.test_schema_v8_state_migrates_to_current_without_losing_fields) ... ok
test_unexpected_conflict_maps_to_integrity_review_not_auto_resolution (test_failure_learning_v0101.FailureLearningCoreTests.test_unexpected_conflict_maps_to_integrity_review_not_auto_resolution) ... ok
test_cli_banner_matches_release_version (test_learning_cycle.LearningCycleCLITests.test_cli_banner_matches_release_version) ... ok
test_feedback_does_not_remove_conflict_from_reasoning (test_learning_cycle.LearningCycleCLITests.test_feedback_does_not_remove_conflict_from_reasoning) ... ok
test_outcome_benchmark_trains_applicability_and_holdout_stays_out_of_ledger (test_learning_cycle.LearningCycleCLITests.test_outcome_benchmark_trains_applicability_and_holdout_stays_out_of_ledger) ... ok
test_positive_feedback_updates_strategy_value_through_cli (test_learning_cycle.LearningCycleCLITests.test_positive_feedback_updates_strategy_value_through_cli) ... ok
test_reasoning_cli_survives_legacy_cp1252_output (test_learning_cycle.LearningCycleCLITests.test_reasoning_cli_survives_legacy_cp1252_output) ... ok
test_strategy_learning_persists_across_cli_restart (test_learning_cycle.LearningCycleCLITests.test_strategy_learning_persists_across_cli_restart) ... ok
test_strategy_outcome_can_be_recorded_against_persisted_reasoning_episode (test_learning_cycle.LearningCycleCLITests.test_strategy_outcome_can_be_recorded_against_persisted_reasoning_episode) ... ok
test_cli_mutation_command_and_report_smoke (test_mutation_lab_v011.MutationLabTests.test_cli_mutation_command_and_report_smoke) ... ok
test_conflict_strategy_cannot_be_mutated_away_from_counterevidence (test_mutation_lab_v011.MutationLabTests.test_conflict_strategy_cannot_be_mutated_away_from_counterevidence) ... ok
test_evaluator_never_touches_users_semantic_memory (test_mutation_lab_v011.MutationLabTests.test_evaluator_never_touches_users_semantic_memory) ... ok
test_holdout_validated_mutation_can_repair_bad_legacy_override (test_mutation_lab_v011.MutationLabTests.test_holdout_validated_mutation_can_repair_bad_legacy_override) ... ok
test_invalid_context_strategy_or_empty_rationale_rejected (test_mutation_lab_v011.MutationLabTests.test_invalid_context_strategy_or_empty_rationale_rejected) ... ok
test_no_improvement_mutation_is_rejected_and_does_not_activate (test_mutation_lab_v011.MutationLabTests.test_no_improvement_mutation_is_rejected_and_does_not_activate) ... ok
test_promoted_policy_changes_primary_focus_but_not_conclusion_or_conflict_safety (test_mutation_lab_v011.MutationLabTests.test_promoted_policy_changes_primary_focus_but_not_conclusion_or_conflict_safety) ... ok
test_reference_evaluator_uses_separate_holdout_and_is_correct_on_all_probes (test_mutation_lab_v011.MutationLabTests.test_reference_evaluator_uses_separate_holdout_and_is_correct_on_all_probes) ... ok
test_root_cause_analysis_adds_specific_debug_signal_to_failure_record (test_mutation_lab_v011.MutationLabTests.test_root_cause_analysis_adds_specific_debug_signal_to_failure_record) ... ok
test_schema_10_migrates_schema_9_and_persists_mutations (test_mutation_lab_v011.MutationLabTests.test_schema_10_migrates_schema_9_and_persists_mutations) ... ok
test_benchmark_fixtures_match_predeclared_strategy_and_conclusion_statuses (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_benchmark_fixtures_match_predeclared_strategy_and_conclusion_statuses) ... ok
test_benchmark_rejects_invalid_mode (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_benchmark_rejects_invalid_mode) ... ok
test_conflict_safety_override_cannot_be_downgraded_by_learned_routing (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_conflict_safety_override_cannot_be_downgraded_by_learned_routing) ... ok
test_declared_task_failure_reduces_applicability_and_persists_with_provenance (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_declared_task_failure_reduces_applicability_and_persists_with_provenance) ... ok
test_failed_diagnostic_outcomes_reduce_applicability_score (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_failed_diagnostic_outcomes_reduce_applicability_score) ... ok
test_holdout_does_not_train_or_change_the_learning_ledger (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_holdout_does_not_train_or_change_the_learning_ledger) ... ok
test_preference_feedback_and_benchmark_outcomes_are_separate_signals (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_preference_feedback_and_benchmark_outcomes_are_separate_signals) ... ok
test_repeated_training_runs_do_not_inflate_trial_counts (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_repeated_training_runs_do_not_inflate_trial_counts) ... ok
test_routing_is_learned_per_context_after_minimum_evaluator_cases (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_routing_is_learned_per_context_after_minimum_evaluator_cases) ... ok
test_schema10_persists_outcomes_and_loads_v7_state (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_schema10_persists_outcomes_and_loads_v7_state) ... ok
test_task_outcome_requires_reasoning_episode_evaluator_and_basis (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_task_outcome_requires_reasoning_episode_evaluator_and_basis) ... ok
test_training_cases_never_pollute_user_semantic_memory (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_training_cases_never_pollute_user_semantic_memory) ... ok
test_unseen_relation_uses_learned_focus_but_preserves_conclusion (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_unseen_relation_uses_learned_focus_but_preserves_conclusion) ... ok
test_conflicting_assertions_are_exposed_but_not_resolved_automatically (test_v03.CognitiveBrainV03Tests.test_conflicting_assertions_are_exposed_but_not_resolved_automatically) ... ok
test_event_trace_exposes_cognitive_cycle (test_v03.CognitiveBrainV03Tests.test_event_trace_exposes_cognitive_cycle) ... ok
test_feedback_updates_persistent_action_value (test_v03.CognitiveBrainV03Tests.test_feedback_updates_persistent_action_value) ... ok
test_negative_feedback_can_change_policy_choice (test_v03.CognitiveBrainV03Tests.test_negative_feedback_can_change_policy_choice) ... ok
test_taught_conditional_can_be_used_for_prediction (test_v03.CognitiveBrainV03Tests.test_taught_conditional_can_be_used_for_prediction) ... ok
test_unknown_condition_reports_gap (test_v03.CognitiveBrainV03Tests.test_unknown_condition_reports_gap) ... ok
test_competing_hypotheses_can_be_compared_by_evidence (test_v04.CognitiveBrainV04Tests.test_competing_hypotheses_can_be_compared_by_evidence) ... ok
test_duplicate_evidence_does_not_inflate_score (test_v04.CognitiveBrainV04Tests.test_duplicate_evidence_does_not_inflate_score) ... ok
test_evidence_updates_assessment_without_verifying_hypothesis (test_v04.CognitiveBrainV04Tests.test_evidence_updates_assessment_without_verifying_hypothesis) ... ok
test_hypothesis_persists_separately_from_semantic_facts (test_v04.CognitiveBrainV04Tests.test_hypothesis_persists_separately_from_semantic_facts) ... ok
test_hypothesis_query_uses_cognitive_process_and_workspace (test_v04.CognitiveBrainV04Tests.test_hypothesis_query_uses_cognitive_process_and_workspace) ... ok
test_invalid_stance_rejected (test_v04.CognitiveBrainV04Tests.test_invalid_stance_rejected) ... ok
test_status_exposes_hypothesis_subsystem_counts (test_v04.CognitiveBrainV04Tests.test_status_exposes_hypothesis_subsystem_counts) ... ok
test_unknown_hypothesis_id_rejected (test_v04.CognitiveBrainV04Tests.test_unknown_hypothesis_id_rejected) ... ok
test_feedback_keeps_targeting_task_not_feedback_episode (test_v05.CognitiveBrainV05Tests.test_feedback_keeps_targeting_task_not_feedback_episode) ... ok
test_goal_changes_are_audited (test_v05.CognitiveBrainV05Tests.test_goal_changes_are_audited) ... ok
test_knowledge_updates_each_get_a_cognitive_cycle_and_episode (test_v05.CognitiveBrainV05Tests.test_knowledge_updates_each_get_a_cognitive_cycle_and_episode) ... ok
test_test_plan_identifies_competing_hypotheses_but_disclaims_heuristics (test_v05.CognitiveBrainV05Tests.test_test_plan_identifies_competing_hypotheses_but_disclaims_heuristics) ... ok
test_unrelated_contradiction_is_not_reported_for_hypothesis_query (test_v05.CognitiveBrainV05Tests.test_unrelated_contradiction_is_not_reported_for_hypothesis_query) ... ok
test_comparison_extracts_shared_outcome_trigger_and_window (test_v06.CognitiveBrainV06Tests.test_comparison_extracts_shared_outcome_trigger_and_window) ... ok
test_exact_repeated_prompt_does_not_echo_as_hippocampal_context (test_v06.CognitiveBrainV06Tests.test_exact_repeated_prompt_does_not_echo_as_hippocampal_context) ... ok
test_hypothesis_verifier_audits_ledger_not_empirical_truth (test_v06.CognitiveBrainV06Tests.test_hypothesis_verifier_audits_ledger_not_empirical_truth) ... ok
test_hypothesis_verifier_detects_malformed_ledger (test_v06.CognitiveBrainV06Tests.test_hypothesis_verifier_detects_malformed_ledger) ... ok
test_hypothesis_verifier_handles_non_numeric_weight_without_crashing (test_v06.CognitiveBrainV06Tests.test_hypothesis_verifier_handles_non_numeric_weight_without_crashing) ... ok
test_verifier_checks_inference_path_without_claiming_truth (test_v06.CognitiveBrainV06Tests.test_verifier_checks_inference_path_without_claiming_truth) ... ok
test_verifier_is_broadcast_during_semantic_query (test_v06.CognitiveBrainV06Tests.test_verifier_is_broadcast_during_semantic_query) ... ok
test_verifier_reports_semantic_conflict (test_v06.CognitiveBrainV06Tests.test_verifier_reports_semantic_conflict) ... ok
test_counterexample_on_inference_path_is_reported (test_v07.CognitiveBrainV07Tests.test_counterexample_on_inference_path_is_reported) ... ok
test_direct_contradiction_is_reported_not_resolved (test_v07.CognitiveBrainV07Tests.test_direct_contradiction_is_reported_not_resolved) ... ok
test_direct_target_assertion_is_not_discarded_due_to_conflicted_alternate_path (test_v07.CognitiveBrainV07Tests.test_direct_target_assertion_is_not_discarded_due_to_conflicted_alternate_path) ... ok
test_invalid_relation_rejected_without_advancing_cycle (test_v07.CognitiveBrainV07Tests.test_invalid_relation_rejected_without_advancing_cycle) ... ok
test_lifetime_counter_has_legacy_fallback (test_v07.CognitiveBrainV07Tests.test_lifetime_counter_has_legacy_fallback) ... ok
test_lifetime_cycle_count_persists_across_sessions (test_v07.CognitiveBrainV07Tests.test_lifetime_cycle_count_persists_across_sessions) ... ok
test_negative_relation_is_cross_checked_against_positive (test_v07.CognitiveBrainV07Tests.test_negative_relation_is_cross_checked_against_positive) ... ok
test_no_path_does_not_claim_target_false (test_v07.CognitiveBrainV07Tests.test_no_path_does_not_claim_target_false) ... ok
test_reasoning_compares_four_distinct_strategies (test_v07.CognitiveBrainV07Tests.test_reasoning_compares_four_distinct_strategies) ... ok
test_reasoning_does_not_reverse_is_a_edges (test_v07.CognitiveBrainV07Tests.test_reasoning_does_not_reverse_is_a_edges) ... ok
test_reasoning_returns_direct_assertion_unverified (test_v07.CognitiveBrainV07Tests.test_reasoning_returns_direct_assertion_unverified) ... ok
test_strategy_comparison_enters_global_workspace_and_episode_memory (test_v07.CognitiveBrainV07Tests.test_strategy_comparison_enters_global_workspace_and_episode_memory) ... ok
test_feedback_after_reason_updates_primary_strategy_preference (test_v08.CognitiveBrainV08Tests.test_feedback_after_reason_updates_primary_strategy_preference) ... ok
test_feedback_for_non_reasoning_episode_does_not_update_strategy_values (test_v08.CognitiveBrainV08Tests.test_feedback_for_non_reasoning_episode_does_not_update_strategy_values) ... ok
test_legacy_memory_loads_without_strategy_learning_fields (test_v08.CognitiveBrainV08Tests.test_legacy_memory_loads_without_strategy_learning_fields) ... ok
test_preference_never_overrides_conflict_conclusion (test_v08.CognitiveBrainV08Tests.test_preference_never_overrides_conflict_conclusion) ... ok
test_repeated_assertion_tracks_mentions_separately_from_unique_sources (test_v08.CognitiveBrainV08Tests.test_repeated_assertion_tracks_mentions_separately_from_unique_sources) ... ok
test_strategy_preference_persists_across_reload (test_v08.CognitiveBrainV08Tests.test_strategy_preference_persists_across_reload) ... ok
test_strategy_snapshot_disclaims_objective_truth (test_v08.CognitiveBrainV08Tests.test_strategy_snapshot_disclaims_objective_truth) ... ok
test_claim_records_with_stable_id_and_deduplicates (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_claim_records_with_stable_id_and_deduplicates) ... ok
test_claim_updates_are_recorded_in_cognitive_cycles (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_claim_updates_are_recorded_in_cognitive_cycles) ... ok
test_corrupt_evidence_reference_fails_audit (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_corrupt_evidence_reference_fails_audit) ... ok
test_evidence_polarities_produce_explicit_conflict (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_evidence_polarities_produce_explicit_conflict) ... ok
test_exact_evidence_duplicate_does_not_inflate_count (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_exact_evidence_duplicate_does_not_inflate_count) ... ok
test_external_check_is_audit_record_not_automatic_truth_promotion (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_external_check_is_audit_record_not_automatic_truth_promotion) ... ok
test_external_check_rejects_unknown_evidence_reference (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_external_check_rejects_unknown_evidence_reference) ... ok
test_invalid_stance_and_unknown_claim_are_rejected (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_invalid_stance_and_unknown_claim_are_rejected) ... ok
test_ledger_report_links_matching_semantic_relation_without_trust_promotion (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_ledger_report_links_matching_semantic_relation_without_trust_promotion) ... ok
test_multiple_records_from_one_source_are_not_counted_as_multiple_source_ids (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_multiple_records_from_one_source_are_not_counted_as_multiple_source_ids) ... ok
test_old_hypothesis_evidence_command_contract_is_preserved (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_old_hypothesis_evidence_command_contract_is_preserved) ... ok
test_persistence_and_legacy_state_migration (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_persistence_and_legacy_state_migration) ... ok
test_saved_state_schema_migrates_forward_to_v10 (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_saved_state_schema_migrates_forward_to_v10) ... ok
test_standalone_ledger_loads_persisted_checks (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_standalone_ledger_loads_persisted_checks) ... ok
test_verifier_audits_provenance_ledger_without_claiming_truth (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_verifier_audits_provenance_ledger_without_claiming_truth) ... ok

----------------------------------------------------------------------
Ran 131 tests in 6.064s

OK

putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python -m brain_ai.cli --memory learning_test_state.json
Human-Inspired Cognitive AI v0.11.0 — tanpa LLM
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
Bahasa sederhana: kucing adalah mamalia; jika hujan maka jalan basah; hipotesis tentang cuaca?

KAMU> kucing adalah mamalia
AI> Saya mencatat relasi: kucing → mamalia (baru). Ini adalah pernyataan pengguna, belum diverifikasi secara independen.
WORKSPACE> perception:observed_input (0.73), prefrontal_cortex:active_goal (0.60), world_model:proposed_relation (0.60)
ACTION> learn_relation (utility=0.95)

KAMU> mamalia adalah hewan
AI> Saya mencatat relasi: mamalia → hewan (baru). Ini adalah pernyataan pengguna, belum diverifikasi secara independen.
WORKSPACE> perception:observed_input (0.66), prefrontal_cortex:active_goal (0.60), hippocampus:episodic_retrieval (0.60)
ACTION> learn_relation (utility=0.85)

KAMU> /reason kucing | is_a | hewan
EPISODE_ID> e67676ba0a00  (gunakan ID ini untuk /strategy-outcome setelah hasil dinilai)
KESIMPULAN> inference_path_unverified
Jalur inferensi ditemukan; premis dan kesimpulannya tetap belum diverifikasi.
STRATEGI UTAMA DIAGNOSTIK> transitive_graph_search (konteks=transitive_inference; mode=safe_rule_fallback_untrained; preferensi umpan balik=0.00; skor applicability benchmark=None)
STRATEGI:
  - direct_lookup: no_direct_match — Tidak ada relasi langsung yang cocok di memori.
  - transitive_graph_search: path_found — Menemukan 1 jalur is_a satu arah.
  - counterevidence_scan: no_stored_counterevidence_found — Tidak ditemukan sanggahan eksplisit pada ruang lingkup yang diperiksa; ini bukan bukti bahwa sanggahan tidak ada.
  - independent_integrity_verifier: integrity_passed_unverified — Jalur dan pembukuan lolos pemeriksaan struktural; konflik semantik (jika ada) dilaporkan terpisah dan fakta tetap belum terverifikasi.
JALUR> kucing → mamalia → hewan
BATASAN> audit memori, bukan verifikasi kebenaran dunia nyata
COGNITIVE_UPDATE> siklus=3; WORKSPACE> reasoning_engine:strategy_transitive_graph_search (0.79), reasoning_engine:multi_strategy_reasoning (0.72), reasoning_engine:strategy_independent_integrity_verifier (0.69)

KAMU> /feedback positive
{
  "reward": 1.0,
  "learning_rate": 0.23,
  "attention_gain": 1.02,
  "policy_update": {
    "action": "compare_reasoning_strategies",
    "episode_id": "e67676ba0a00",
    "old_value": 0.0,
    "new_value": 0.2,
    "strategy_update": {
      "strategy": "transitive_graph_search",
      "old_value": 0.0,
      "new_value": 0.2,
      "feedback_count": 1,
      "interpretation": "preferensi pengguna terhadap respons penalaran; bukan ukuran kebenaran objektif"
    }
  },
  "strategy_learning": {
    "transitive_graph_search": {
      "user_feedback_value": 0.2,
      "feedback_count": 1,
      "meaning": "preferensi pengguna, bukan akurasi faktual atau bukti kebenaran"
    }
  },
  "strategy_applicability_learning": {},
  "strategy_benchmark_training_trials": 0,
  "strategy_declared_outcomes": 0,
  "failure_diagnoses": 0,
  "reusable_strategy_lessons": 0,
  "strategy_mutations": 0,
  "active_strategy_policy_overrides": {},
  "action_values": {
    "compare_reasoning_strategies": 0.2
  },
  "cognitive_cycle": 4,
  "broadcast": [
    {
      "source": "neuromodulator",
      "kind": "feedback_update",
      "content": {
        "reward": 1.0,
        "policy_update": {
          "action": "compare_reasoning_strategies",
          "episode_id": "e67676ba0a00",
          "old_value": 0.0,
          "new_value": 0.2,
          "strategy_update": {
            "strategy": "transitive_graph_search",
            "old_value": 0.0,
            "new_value": 0.2,
            "feedback_count": 1,
            "interpretation": "preferensi pengguna terhadap respons penalaran; bukan ukuran kebenaran objektif"
          }
        }
      },
      "confidence": 0.95,
      "novelty": 0.35,
      "urgency": 0.0,
      "goal_relevance": 0.95,
      "evidence": [
        "perubahan atau rencana berasal dari perintah eksplisit pengguna"
      ],
      "score": 0.6399999999999999
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
  ],
  "events": [
    {
      "sequence": 38,
      "event_id": "42152331a954",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "perception",
      "event_type": "input_received",
      "payload": {
        "text": "/feedback positive",
        "channel": "structured_command"
      }
    },
    {
      "sequence": 39,
      "event_id": "4a808389f5c9",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "language_area",
      "event_type": "command_parsed",
      "payload": {
        "command_kind": "outcome_feedback"
      }
    },
    {
      "sequence": 40,
      "event_id": "f7ffa9b23057",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "prefrontal_cortex",
      "event_type": "candidate_proposed",
      "payload": {
        "kind": "active_goal",
        "confidence": 0.9,
        "content": {
          "goal": "memahami input dan merespons dengan jujur",
          "task_kind": "structured_command"
        }
      }
    },
    {
      "sequence": 41,
      "event_id": "bbac0625dd18",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "neuromodulator",
      "event_type": "candidate_proposed",
      "payload": {
        "kind": "feedback_update",
        "confidence": 0.95,
        "content": {
          "reward": 1.0,
          "policy_update": {
            "action": "compare_reasoning_strategies",
            "episode_id": "e67676ba0a00",
            "old_value": 0.0,
            "new_value": 0.2,
            "strategy_update": {
              "strategy": "transitive_graph_search",
              "old_value": 0.0,
              "new_value": 0.2,
              "feedback_count": 1,
              "interpretation": "preferensi pengguna terhadap respons penalaran; bukan ukuran kebenaran objektif"
            }
          }
        }
      }
    },
    {
      "sequence": 42,
      "event_id": "e7a7721e5eb1",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "global_workspace",
      "event_type": "workspace_broadcast",
      "payload": {
        "items": [
          {
            "source": "neuromodulator",
            "kind": "feedback_update",
            "score": 0.64
          },
          {
            "source": "prefrontal_cortex",
            "kind": "active_goal",
            "score": 0.615
          }
        ]
      }
    },
    {
      "sequence": 43,
      "event_id": "6855d2b4315a",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "neuromodulator",
      "event_type": "feedback_applied",
      "payload": {
        "reward": 1.0,
        "policy_update": {
          "action": "compare_reasoning_strategies",
          "episode_id": "e67676ba0a00",
          "old_value": 0.0,
          "new_value": 0.2,
          "strategy_update": {
            "strategy": "transitive_graph_search",
            "old_value": 0.0,
            "new_value": 0.2,
            "feedback_count": 1,
            "interpretation": "preferensi pengguna terhadap respons penalaran; bukan ukuran kebenaran objektif"
          }
        }
      }
    },
    {
      "sequence": 44,
      "event_id": "ce8ba150ef82",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "executive_controller",
      "event_type": "command_executed",
      "payload": {
        "action": "apply_feedback",
        "mode": "explicit_user_command"
      }
    },
    {
      "sequence": 45,
      "event_id": "9fa8274a3840",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "language_area",
      "event_type": "response_generated",
      "payload": {
        "action": "apply_feedback",
        "response": "Umpan balik positive diterapkan."
      }
    },
    {
      "sequence": 46,
      "event_id": "bc4ec6792032",
      "timestamp": "2026-10-21T13:53:06.305443+00:00",
      "cycle": 4,
      "source": "hippocampus",
      "event_type": "episode_stored",
      "payload": {
        "episode_id": "1c9eb1eec8f9",
        "action": "apply_feedback",
        "interaction_type": "structured_command"
      }
    }
  ],
  "episode_id": "1c9eb1eec8f9"
}

KAMU> /learning-benchmark train
{
  "benchmark_version": "strategy-applicability-v1",
  "requested_mode": "train",
  "cases_run": 16,
  "training_trials_added": 64,
  "conclusion_accuracy": 1.0,
  "strategy_status_accuracy": 1.0,
  "learned_routing_accuracy": 1.0,
  "routed_cases": 16,
  "strategy_statuses_correct": 64,
  "strategy_statuses_total": 64,
  "context_summary": {
    "direct_relation": {
      "cases": 4,
      "conclusions_correct": 4,
      "expected_focus_matches": 4,
      "expected_focus_total": 4
    },
    "transitive_inference": {
      "cases": 4,
      "conclusions_correct": 4,
      "expected_focus_matches": 4,
      "expected_focus_total": 4
    },
    "conflict_detection": {
      "cases": 4,
      "conclusions_correct": 4,
      "expected_focus_matches": 4,
      "expected_focus_total": 4
    },
    "unsupported_claim": {
      "cases": 4,
      "conclusions_correct": 4,
      "expected_focus_matches": 4,
      "expected_focus_total": 4
    }
  },
  "cases": [
    {
      "case_id": "train_direct_01",
      "split": "train",
      "context": "direct_relation",
      "query": {
        "subject": "kucing",
        "relation": "is_a",
        "object": "mamalia"
      },
      "expected_conclusion": "direct_assertion_unverified",
      "observed_conclusion": "direct_assertion_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "direct_lookup",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_direct_02",
      "split": "train",
      "context": "direct_relation",
      "query": {
        "subject": "air",
        "relation": "is_a",
        "object": "cairan"
      },
      "expected_conclusion": "direct_assertion_unverified",
      "observed_conclusion": "direct_assertion_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "direct_lookup",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_direct_03",
      "split": "train",
      "context": "direct_relation",
      "query": {
        "subject": "mawar",
        "relation": "is_a",
        "object": "tumbuhan"
      },
      "expected_conclusion": "direct_assertion_unverified",
      "observed_conclusion": "direct_assertion_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "direct_lookup",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_direct_04",
      "split": "train",
      "context": "direct_relation",
      "query": {
        "subject": "pipit",
        "relation": "is_a",
        "object": "burung"
      },
      "expected_conclusion": "direct_assertion_unverified",
      "observed_conclusion": "direct_assertion_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "direct_lookup",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_transitive_01",
      "split": "train",
      "context": "transitive_inference",
      "query": {
        "subject": "kucing",
        "relation": "is_a",
        "object": "hewan"
      },
      "expected_conclusion": "inference_path_unverified",
      "observed_conclusion": "inference_path_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_transitive_02",
      "split": "train",
      "context": "transitive_inference",
      "query": {
        "subject": "mawar",
        "relation": "is_a",
        "object": "organisme"
      },
      "expected_conclusion": "inference_path_unverified",
      "observed_conclusion": "inference_path_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_transitive_03",
      "split": "train",
      "context": "transitive_inference",
      "query": {
        "subject": "elang",
        "relation": "is_a",
        "object": "organisme"
      },
      "expected_conclusion": "inference_path_unverified",
      "observed_conclusion": "inference_path_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_transitive_04",
      "split": "train",
      "context": "transitive_inference",
      "query": {
        "subject": "ikan",
        "relation": "is_a",
        "object": "hewan"
      },
      "expected_conclusion": "inference_path_unverified",
      "observed_conclusion": "inference_path_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_conflict_01",
      "split": "train",
      "context": "conflict_detection",
      "query": {
        "subject": "kucing",
        "relation": "is_a",
        "object": "mamalia"
      },
      "expected_conclusion": "conflicted",
      "observed_conclusion": "conflicted",
      "conclusion_correct": true,
      "expected_focus_strategy": "counterevidence_scan",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "counterevidence_found",
          "observed": "counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_conflict_02",
      "split": "train",
      "context": "conflict_detection",
      "query": {
        "subject": "air",
        "relation": "is_a",
        "object": "cairan"
      },
      "expected_conclusion": "conflicted",
      "observed_conclusion": "conflicted",
      "conclusion_correct": true,
      "expected_focus_strategy": "counterevidence_scan",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "counterevidence_found",
          "observed": "counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_conflict_03",
      "split": "train",
      "context": "conflict_detection",
      "query": {
        "subject": "mawar",
        "relation": "is_a",
        "object": "tumbuhan"
      },
      "expected_conclusion": "conflicted",
      "observed_conclusion": "conflicted",
      "conclusion_correct": true,
      "expected_focus_strategy": "counterevidence_scan",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "counterevidence_found",
          "observed": "counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_conflict_04",
      "split": "train",
      "context": "conflict_detection",
      "query": {
        "subject": "pipit",
        "relation": "is_a",
        "object": "burung"
      },
      "expected_conclusion": "conflicted",
      "observed_conclusion": "conflicted",
      "conclusion_correct": true,
      "expected_focus_strategy": "counterevidence_scan",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "counterevidence_found",
          "observed": "counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_unsupported_01",
      "split": "train",
      "context": "unsupported_claim",
      "query": {
        "subject": "kucing",
        "relation": "is_a",
        "object": "reptil"
      },
      "expected_conclusion": "no_support_found_in_stored_memory",
      "observed_conclusion": "no_support_found_in_stored_memory",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "no_path_found",
          "observed": "no_path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "nothing_to_verify",
          "observed": "nothing_to_verify",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_unsupported_02",
      "split": "train",
      "context": "unsupported_claim",
      "query": {
        "subject": "laptop",
        "relation": "is_a",
        "object": "mamalia"
      },
      "expected_conclusion": "no_support_found_in_stored_memory",
      "observed_conclusion": "no_support_found_in_stored_memory",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "no_path_found",
          "observed": "no_path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "nothing_to_verify",
          "observed": "nothing_to_verify",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_unsupported_03",
      "split": "train",
      "context": "unsupported_claim",
      "query": {
        "subject": "samudra",
        "relation": "is_a",
        "object": "planet"
      },
      "expected_conclusion": "no_support_found_in_stored_memory",
      "observed_conclusion": "no_support_found_in_stored_memory",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "no_path_found",
          "observed": "no_path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "nothing_to_verify",
          "observed": "nothing_to_verify",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "train_unsupported_04",
      "split": "train",
      "context": "unsupported_claim",
      "query": {
        "subject": "api",
        "relation": "is_a",
        "object": "tumbuhan"
      },
      "expected_conclusion": "no_support_found_in_stored_memory",
      "observed_conclusion": "no_support_found_in_stored_memory",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "no_path_found",
          "observed": "no_path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "nothing_to_verify",
          "observed": "nothing_to_verify",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    }
  ],
  "holdout_not_added_to_training_ledger": false,
  "epistemic_note": "Ini evaluasi deterministik terhadap status strategi dan label fokus pada benchmark buatan; bukan validasi fakta dunia nyata, dan belum membuktikan peningkatan pada tugas bahasa umum."
}

KAMU> /learning-benchmark holdout
{
  "benchmark_version": "strategy-applicability-v1",
  "requested_mode": "holdout",
  "cases_run": 8,
  "training_trials_added": 0,
  "conclusion_accuracy": 1.0,
  "strategy_status_accuracy": 1.0,
  "learned_routing_accuracy": 1.0,
  "routed_cases": 8,
  "strategy_statuses_correct": 32,
  "strategy_statuses_total": 32,
  "context_summary": {
    "direct_relation": {
      "cases": 2,
      "conclusions_correct": 2,
      "expected_focus_matches": 2,
      "expected_focus_total": 2
    },
    "transitive_inference": {
      "cases": 2,
      "conclusions_correct": 2,
      "expected_focus_matches": 2,
      "expected_focus_total": 2
    },
    "conflict_detection": {
      "cases": 2,
      "conclusions_correct": 2,
      "expected_focus_matches": 2,
      "expected_focus_total": 2
    },
    "unsupported_claim": {
      "cases": 2,
      "conclusions_correct": 2,
      "expected_focus_matches": 2,
      "expected_focus_total": 2
    }
  },
  "cases": [
    {
      "case_id": "holdout_direct_01",
      "split": "holdout",
      "context": "direct_relation",
      "query": {
        "subject": "laptop",
        "relation": "is_a",
        "object": "perangkat"
      },
      "expected_conclusion": "direct_assertion_unverified",
      "observed_conclusion": "direct_assertion_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "direct_lookup",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_direct_02",
      "split": "holdout",
      "context": "direct_relation",
      "query": {
        "subject": "paus",
        "relation": "is_a",
        "object": "mamalia"
      },
      "expected_conclusion": "direct_assertion_unverified",
      "observed_conclusion": "direct_assertion_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "direct_lookup",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_transitive_01",
      "split": "holdout",
      "context": "transitive_inference",
      "query": {
        "subject": "komputer",
        "relation": "is_a",
        "object": "entitas"
      },
      "expected_conclusion": "inference_path_unverified",
      "observed_conclusion": "inference_path_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_transitive_02",
      "split": "holdout",
      "context": "transitive_inference",
      "query": {
        "subject": "elang",
        "relation": "is_a",
        "object": "hewan"
      },
      "expected_conclusion": "inference_path_unverified",
      "observed_conclusion": "inference_path_unverified",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_conflict_01",
      "split": "holdout",
      "context": "conflict_detection",
      "query": {
        "subject": "laptop",
        "relation": "is_a",
        "object": "perangkat"
      },
      "expected_conclusion": "conflicted",
      "observed_conclusion": "conflicted",
      "conclusion_correct": true,
      "expected_focus_strategy": "counterevidence_scan",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "counterevidence_found",
          "observed": "counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_conflict_02",
      "split": "holdout",
      "context": "conflict_detection",
      "query": {
        "subject": "paus",
        "relation": "is_a",
        "object": "mamalia"
      },
      "expected_conclusion": "conflicted",
      "observed_conclusion": "conflicted",
      "conclusion_correct": true,
      "expected_focus_strategy": "counterevidence_scan",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "match_found",
          "observed": "match_found",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "path_found",
          "observed": "path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "counterevidence_found",
          "observed": "counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "integrity_passed_unverified",
          "observed": "integrity_passed_unverified",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_unsupported_01",
      "split": "holdout",
      "context": "unsupported_claim",
      "query": {
        "subject": "bunga",
        "relation": "is_a",
        "object": "logam"
      },
      "expected_conclusion": "no_support_found_in_stored_memory",
      "observed_conclusion": "no_support_found_in_stored_memory",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "no_path_found",
          "observed": "no_path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "nothing_to_verify",
          "observed": "nothing_to_verify",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    },
    {
      "case_id": "holdout_unsupported_02",
      "split": "holdout",
      "context": "unsupported_claim",
      "query": {
        "subject": "batu",
        "relation": "is_a",
        "object": "reptil"
      },
      "expected_conclusion": "no_support_found_in_stored_memory",
      "observed_conclusion": "no_support_found_in_stored_memory",
      "conclusion_correct": true,
      "expected_focus_strategy": "transitive_graph_search",
      "strategy_statuses": {
        "direct_lookup": {
          "expected": "no_direct_match",
          "observed": "no_direct_match",
          "correct": true
        },
        "transitive_graph_search": {
          "expected": "no_path_found",
          "observed": "no_path_found",
          "correct": true
        },
        "counterevidence_scan": {
          "expected": "no_stored_counterevidence_found",
          "observed": "no_stored_counterevidence_found",
          "correct": true
        },
        "independent_integrity_verifier": {
          "expected": "nothing_to_verify",
          "observed": "nothing_to_verify",
          "correct": true
        }
      },
      "all_strategy_statuses_correct": true
    }
  ],
  "holdout_not_added_to_training_ledger": true,
  "epistemic_note": "Ini evaluasi deterministik terhadap status strategi dan label fokus pada benchmark buatan; bukan validasi fakta dunia nyata, dan belum membuktikan peningkatan pada tugas bahasa umum."
}

KAMU> /learning-report
{
  "training_trials": 64,
  "declared_task_outcomes": 0,
  "applicability_by_context": {
    "conflict_detection": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "counterevidence_scan",
        "transitive_graph_search",
        "independent_integrity_verifier",
        "direct_lookup"
      ],
      "recommended_strategy": "counterevidence_scan",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    },
    "direct_relation": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "direct_lookup",
        "transitive_graph_search",
        "independent_integrity_verifier",
        "counterevidence_scan"
      ],
      "recommended_strategy": "direct_lookup",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    },
    "transitive_inference": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "transitive_graph_search",
        "independent_integrity_verifier",
        "direct_lookup",
        "counterevidence_scan"
      ],
      "recommended_strategy": "transitive_graph_search",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    },
    "unsupported_claim": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "transitive_graph_search",
        "independent_integrity_verifier",
        "direct_lookup",
        "counterevidence_scan"
      ],
      "recommended_strategy": "transitive_graph_search",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    }
  },
  "user_feedback_preferences": {
    "transitive_graph_search": {
      "user_feedback_value": 0.2,
      "feedback_count": 1,
      "meaning": "preferensi pengguna, bukan akurasi faktual atau bukti kebenaran"
    }
  },
  "interpretation": "Outcome benchmark dan preferensi pengguna adalah sinyal terpisah; ini bukan verifikasi fakta eksternal."
}

KAMU> /status
{
  "workspace": {
    "cycle": 4,
    "goal": "memahami input dan merespons dengan jujur",
    "arousal": 0.25,
    "learning_rate": 0.23,
    "prediction_error": 0.15,
    "last_action": "apply_feedback",
    "working_memory_size": 7,
    "broadcast": [
      {
        "source": "neuromodulator",
        "kind": "feedback_update",
        "content": {
          "reward": 1.0,
          "policy_update": {
            "action": "compare_reasoning_strategies",
            "episode_id": "e67676ba0a00",
            "old_value": 0.0,
            "new_value": 0.2,
            "strategy_update": {
              "strategy": "transitive_graph_search",
              "old_value": 0.0,
              "new_value": 0.2,
              "feedback_count": 1,
              "interpretation": "preferensi pengguna terhadap respons penalaran; bukan ukuran kebenaran objektif"
            }
          }
        },
        "confidence": 0.95,
        "novelty": 0.35,
        "urgency": 0.0,
        "goal_relevance": 0.95,
        "evidence": [
          "perubahan atau rencana berasal dari perintah eksplisit pengguna"
        ],
        "score": 0.6399999999999999
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
  "cognitive_cycles_this_run": 4,
  "cognitive_cycles_total": 4,
  "episodic_memories": 4,
  "semantic_relations": 2,
  "hypotheses": 0,
  "hypothesis_evidence_records": 0,
  "provenance_claims": 0,
  "provenance_evidence_records": 0,
  "provenance_external_checks": 0,
  "memory_schema_version": 10,
  "feedback_count": 1,
  "average_reward": 1.0,
  "action_values": {
    "compare_reasoning_strategies": 0.2
  },
  "strategy_learning": {
    "transitive_graph_search": {
      "user_feedback_value": 0.2,
      "feedback_count": 1,
      "meaning": "preferensi pengguna, bukan akurasi faktual atau bukti kebenaran"
    }
  },
  "strategy_applicability_learning": {
    "conflict_detection": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "counterevidence_scan",
        "transitive_graph_search",
        "independent_integrity_verifier",
        "direct_lookup"
      ],
      "recommended_strategy": "counterevidence_scan",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    },
    "direct_relation": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "direct_lookup",
        "transitive_graph_search",
        "independent_integrity_verifier",
        "counterevidence_scan"
      ],
      "recommended_strategy": "direct_lookup",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    },
    "transitive_inference": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "transitive_graph_search",
        "independent_integrity_verifier",
        "direct_lookup",
        "counterevidence_scan"
      ],
      "recommended_strategy": "transitive_graph_search",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    },
    "unsupported_claim": {
      "strategies": {
        "direct_lookup": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "transitive_graph_search": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.8333,
          "applicability_success_weight": 4.0,
          "curated_focus_label_hits": 4,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "counterevidence_scan": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        },
        "independent_integrity_verifier": {
          "training_cases": 4,
          "benchmark_cases": 4,
          "declared_task_outcomes": 0,
          "status_accuracy": 1.0,
          "applicability_score": 0.1667,
          "applicability_success_weight": 0.0,
          "curated_focus_label_hits": 0,
          "task_outcome_counts": {
            "success": 0,
            "partial": 0,
            "failure": 0
          },
          "eligible_for_routing": true,
          "evaluator_scope": "benchmark=fixture deterministik; task outcome=deklarasi evaluator yang belum diverifikasi independen"
        }
      },
      "ranking": [
        "transitive_graph_search",
        "independent_integrity_verifier",
        "direct_lookup",
        "counterevidence_scan"
      ],
      "recommended_strategy": "transitive_graph_search",
      "training_cases_per_strategy": 4,
      "minimum_cases_required": 2,
      "routing_enabled": true,
      "meaning": "kesesuaian fokus diagnostik berdasarkan benchmark dan outcome yang dinilai; bukan akurasi kebenaran dunia nyata"
    }
  },
  "strategy_benchmark_training_trials": 64,
  "strategy_declared_outcomes": 0,
  "failure_diagnoses": 0,
  "reusable_strategy_lessons": 0,
  "strategy_mutations": 0,
  "active_strategy_policy_overrides": {},
  "unresolved_contradictions": [],
  "event_count_this_run": 46,
  "needs": {
    "energy": 0.99,
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
    "independent_verifier",
    "multi_strategy_reasoner",
    "global_workspace"
  ],
  "llm_used": false
}

KAMU> /quit
Memori disimpan. Sampai jumpa.

putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python scripts/verify_release.py
PASS | compileall |
PASS | cumulative_unittest_131 | exit=0, tests=131
PASS | cli_smoke_utf-8 | exit=0; markers=True; bytes=56190
PASS | cli_smoke_cp1252 | exit=0; markers=True; bytes=56200

Release verification: PASS; 4/4 gates passed.

putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python -m brain_ai.cli
Human-Inspired Cognitive AI v0.11.0 — tanpa LLM
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
Bahasa sederhana: kucing adalah mamalia; jika hujan maka jalan basah; hipotesis tentang cuaca?

KAMU> quokka adalah mamalia
AI> Saya mencatat relasi: quokka → mamalia (baru). Ini adalah pernyataan pengguna, belum diverifikasi secara independen.
WORKSPACE> perception:observed_input (0.73), prefrontal_cortex:active_goal (0.60), world_model:proposed_relation (0.60)
ACTION> learn_relation (utility=0.95)

KAMU> /reason quokka | is_a | mamalia
EPISODE_ID> 96f511cd05ed  (gunakan ID ini untuk /strategy-outcome setelah hasil dinilai)
KESIMPULAN> direct_assertion_unverified
Relasi langsung ditemukan, tetapi belum diverifikasi terhadap dunia nyata.
STRATEGI UTAMA DIAGNOSTIK> direct_lookup (konteks=direct_relation; mode=safe_rule_fallback_untrained; preferensi umpan balik=0.00; skor applicability benchmark=None)
STRATEGI:
  - direct_lookup: match_found — Ditemukan 1 relasi langsung yang cocok.
  - transitive_graph_search: path_found — Menemukan 1 jalur is_a satu arah.
  - counterevidence_scan: no_stored_counterevidence_found — Tidak ditemukan sanggahan eksplisit pada ruang lingkup yang diperiksa; ini bukan bukti bahwa sanggahan tidak ada.
  - independent_integrity_verifier: integrity_passed_unverified — Jalur dan pembukuan lolos pemeriksaan struktural; konflik semantik (jika ada) dilaporkan terpisah dan fakta tetap belum terverifikasi.
JALUR> quokka → mamalia
BATASAN> audit memori, bukan verifikasi kebenaran dunia nyata
COGNITIVE_UPDATE> siklus=2; WORKSPACE> reasoning_engine:strategy_direct_lookup (0.79), reasoning_engine:multi_strategy_reasoning (0.72), reasoning_engine:strategy_transitive_graph_search (0.69)

KAMU> /failure-diagnose EPISODE_ID_ANDA | conflicted | evaluator:qa-1 | Ekspektasi berasal dari fixture konflik yang ditetapkan sebelum tes.
Diagnosis kegagalan gagal: Episode bukan hasil /reason tersimpan dengan metadata v0.10.1 yang cukup untuk diagnosis.

KAMU> /failure-report
{
  "diagnosis_count": 0,
  "mismatch_count": 0,
  "lessons": [],
  "recent_diagnoses": [],
  "lesson_application_policy": "Repeated candidates are surfaced as advisory Global Workspace items only; they do not rewrite facts, conclusions, or verifier verdicts. Distinct caller-supplied evaluator IDs are not authenticated independence."
}

KAMU> /status
{
  "workspace": {
    "cycle": 2,
    "goal": "memahami input dan merespons dengan jujur",
    "arousal": 0.25,
    "learning_rate": 0.2,
    "prediction_error": 0.05,
    "last_action": "compare_reasoning_strategies",
    "working_memory_size": 7,
    "broadcast": [
      {
        "source": "reasoning_engine",
        "kind": "strategy_direct_lookup",
        "content": {
          "strategy": "direct_lookup",
          "status": "match_found",
          "finding": "Ditemukan 1 relasi langsung yang cocok.",
          "user_feedback_value": 0.0,
          "user_feedback_count": 0,
          "benchmark_applicability_score": null,
          "selected_as_primary_focus": true
        },
        "confidence": 0.86,
        "novelty": 0.65,
        "urgency": 0.65,
        "goal_relevance": 0.95,
        "evidence": [
          "hasil strategi dari memori terstruktur; tidak mengonfirmasi fakta eksternal"
        ],
        "score": 0.7913499999999999
      },
      {
        "source": "reasoning_engine",
        "kind": "multi_strategy_reasoning",
        "content": {
          "query": {
            "subject": "quokka",
            "relation": "is_a",
            "object": "mamalia"
          },
          "conclusion_status": "direct_assertion_unverified",
          "selected_diagnostic_strategy": "direct_lookup",
          "primary_strategy": "direct_lookup",
          "primary_strategy_user_feedback_value": 0.0,
          "strategy_count": 4,
          "counterevidence_count": 0
        },
        "confidence": 0.95,
        "novelty": 0.8,
        "urgency": 0.0,
        "goal_relevance": 0.95,
        "evidence": [
          "perubahan atau rencana berasal dari perintah eksplisit pengguna"
        ],
        "score": 0.7153999999999999
      },
      {
        "source": "reasoning_engine",
        "kind": "strategy_transitive_graph_search",
        "content": {
          "strategy": "transitive_graph_search",
          "status": "path_found",
          "finding": "Menemukan 1 jalur is_a satu arah.",
          "user_feedback_value": 0.0,
          "user_feedback_count": 0,
          "benchmark_applicability_score": null,
          "selected_as_primary_focus": false
        },
        "confidence": 0.86,
        "novelty": 0.65,
        "urgency": 0.15,
        "goal_relevance": 0.95,
        "evidence": [
          "hasil strategi dari memori terstruktur; tidak mengonfirmasi fakta eksternal"
        ],
        "score": 0.69335
      }
    ]
  },
  "cognitive_cycles_this_run": 2,
  "cognitive_cycles_total": 2,
  "episodic_memories": 2,
  "semantic_relations": 1,
  "hypotheses": 0,
  "hypothesis_evidence_records": 0,
  "provenance_claims": 0,
  "provenance_evidence_records": 0,
  "provenance_external_checks": 0,
  "memory_schema_version": 10,
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
  "unresolved_contradictions": [],
  "event_count_this_run": 24,
  "needs": {
    "energy": 0.995,
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
    "independent_verifier",
    "multi_strategy_reasoner",
    "global_workspace"
  ],
  "llm_used": false
}

KAMU> /mutation-report
{
  "evaluator_id": "cognitive-policy-holdout-v1",
  "active_policy": {
    "direct_relation": "direct_lookup",
    "transitive_inference": "transitive_graph_search",
    "conflict_detection": "counterevidence_scan",
    "unsupported_claim": "transitive_graph_search"
  },
  "active_overrides": {},
  "mutation_count": 0,
  "promoted_count": 0,
  "rejected_or_no_improvement_count": 0,
  "mutations": [],
  "scope_note": "Policy aktif hanya berubah setelah kenaikan routing yang ketat, kesimpulan tetap benar pada semua probe, dan invariant konflik lulus."
}

KAMU> /mutation-propose direct_relation | transitive_graph_search | Uji apakah pencarian graf lebih tepat untuk klaim langsung
{
  "mutation": {
    "mutation_id": "MU00001",
    "mutation_type": "context_focus_override",
    "context": "direct_relation",
    "candidate_strategy": "transitive_graph_search",
    "rationale": "Uji apakah pencarian graf lebih tepat untuk klaim langsung",
    "baseline_policy": {
      "direct_relation": "direct_lookup",
      "transitive_inference": "transitive_graph_search",
      "conflict_detection": "counterevidence_scan",
      "unsupported_claim": "transitive_graph_search"
    },
    "candidate_policy": {
      "direct_relation": "transitive_graph_search",
      "transitive_inference": "transitive_graph_search",
      "conflict_detection": "counterevidence_scan",
      "unsupported_claim": "transitive_graph_search"
    },
    "baseline_evaluation": {
      "evaluator_id": "cognitive-policy-holdout-v1",
      "suite_version": "cognitive-policy-holdout-v1",
      "case_count": 12,
      "conclusion_accuracy": 1.0,
      "routing_accuracy": 1.0,
      "conclusion_cases_correct": 12,
      "routing_cases_correct": 12,
      "safety_pass": true,
      "safety_failures": [],
      "holdout_case_ids": [
        "policy_direct_a",
        "policy_direct_b",
        "policy_direct_c",
        "policy_path_a",
        "policy_path_b",
        "policy_path_c",
        "policy_conflict_a",
        "policy_conflict_b",
        "policy_conflict_c",
        "policy_unsupported_a",
        "policy_unsupported_b",
        "policy_unsupported_c"
      ],
      "training_ledger_write_count": 0,
      "cases": [
        {
          "case_id": "policy_direct_a",
          "context": "direct_relation",
          "expected_conclusion": "direct_assertion_unverified",
          "observed_conclusion": "direct_assertion_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "direct_lookup",
          "selected_focus_strategy": "direct_lookup",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_direct_b",
          "context": "direct_relation",
          "expected_conclusion": "direct_assertion_unverified",
          "observed_conclusion": "direct_assertion_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "direct_lookup",
          "selected_focus_strategy": "direct_lookup",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_direct_c",
          "context": "direct_relation",
          "expected_conclusion": "direct_assertion_unverified",
          "observed_conclusion": "direct_assertion_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "direct_lookup",
          "selected_focus_strategy": "direct_lookup",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_path_a",
          "context": "transitive_inference",
          "expected_conclusion": "inference_path_unverified",
          "observed_conclusion": "inference_path_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_path_b",
          "context": "transitive_inference",
          "expected_conclusion": "inference_path_unverified",
          "observed_conclusion": "inference_path_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_path_c",
          "context": "transitive_inference",
          "expected_conclusion": "inference_path_unverified",
          "observed_conclusion": "inference_path_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_conflict_a",
          "context": "conflict_detection",
          "expected_conclusion": "conflicted",
          "observed_conclusion": "conflicted",
          "conclusion_correct": true,
          "expected_focus_strategy": "counterevidence_scan",
          "selected_focus_strategy": "counterevidence_scan",
          "routing_correct": true,
          "counterevidence_present": true,
          "safety_pass": true
        },
        {
          "case_id": "policy_conflict_b",
          "context": "conflict_detection",
          "expected_conclusion": "conflicted",
          "observed_conclusion": "conflicted",
          "conclusion_correct": true,
          "expected_focus_strategy": "counterevidence_scan",
          "selected_focus_strategy": "counterevidence_scan",
          "routing_correct": true,
          "counterevidence_present": true,
          "safety_pass": true
        },
        {
          "case_id": "policy_conflict_c",
          "context": "conflict_detection",
          "expected_conclusion": "conflicted",
          "observed_conclusion": "conflicted",
          "conclusion_correct": true,
          "expected_focus_strategy": "counterevidence_scan",
          "selected_focus_strategy": "counterevidence_scan",
          "routing_correct": true,
          "counterevidence_present": true,
          "safety_pass": true
        },
        {
          "case_id": "policy_unsupported_a",
          "context": "unsupported_claim",
          "expected_conclusion": "no_support_found_in_stored_memory",
          "observed_conclusion": "no_support_found_in_stored_memory",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_unsupported_b",
          "context": "unsupported_claim",
          "expected_conclusion": "no_support_found_in_stored_memory",
          "observed_conclusion": "no_support_found_in_stored_memory",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_unsupported_c",
          "context": "unsupported_claim",
          "expected_conclusion": "no_support_found_in_stored_memory",
          "observed_conclusion": "no_support_found_in_stored_memory",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        }
      ],
      "epistemic_status": "curated_reference_evaluation_not_external_truth_verification",
      "scope_note": "Suite ini memiliki jalur kode dan fixture terpisah dari training benchmark v0.10. Ia memeriksa perilaku program relatif terhadap label yang ditetapkan sebelumnya; bukan penilai eksternal independen dan bukan bukti kebenaran dunia nyata."
    },
    "candidate_evaluation": {
      "evaluator_id": "cognitive-policy-holdout-v1",
      "suite_version": "cognitive-policy-holdout-v1",
      "case_count": 12,
      "conclusion_accuracy": 1.0,
      "routing_accuracy": 0.75,
      "conclusion_cases_correct": 12,
      "routing_cases_correct": 9,
      "safety_pass": true,
      "safety_failures": [],
      "holdout_case_ids": [
        "policy_direct_a",
        "policy_direct_b",
        "policy_direct_c",
        "policy_path_a",
        "policy_path_b",
        "policy_path_c",
        "policy_conflict_a",
        "policy_conflict_b",
        "policy_conflict_c",
        "policy_unsupported_a",
        "policy_unsupported_b",
        "policy_unsupported_c"
      ],
      "training_ledger_write_count": 0,
      "cases": [
        {
          "case_id": "policy_direct_a",
          "context": "direct_relation",
          "expected_conclusion": "direct_assertion_unverified",
          "observed_conclusion": "direct_assertion_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "direct_lookup",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": false,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_direct_b",
          "context": "direct_relation",
          "expected_conclusion": "direct_assertion_unverified",
          "observed_conclusion": "direct_assertion_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "direct_lookup",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": false,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_direct_c",
          "context": "direct_relation",
          "expected_conclusion": "direct_assertion_unverified",
          "observed_conclusion": "direct_assertion_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "direct_lookup",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": false,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_path_a",
          "context": "transitive_inference",
          "expected_conclusion": "inference_path_unverified",
          "observed_conclusion": "inference_path_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_path_b",
          "context": "transitive_inference",
          "expected_conclusion": "inference_path_unverified",
          "observed_conclusion": "inference_path_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_path_c",
          "context": "transitive_inference",
          "expected_conclusion": "inference_path_unverified",
          "observed_conclusion": "inference_path_unverified",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_conflict_a",
          "context": "conflict_detection",
          "expected_conclusion": "conflicted",
          "observed_conclusion": "conflicted",
          "conclusion_correct": true,
          "expected_focus_strategy": "counterevidence_scan",
          "selected_focus_strategy": "counterevidence_scan",
          "routing_correct": true,
          "counterevidence_present": true,
          "safety_pass": true
        },
        {
          "case_id": "policy_conflict_b",
          "context": "conflict_detection",
          "expected_conclusion": "conflicted",
          "observed_conclusion": "conflicted",
          "conclusion_correct": true,
          "expected_focus_strategy": "counterevidence_scan",
          "selected_focus_strategy": "counterevidence_scan",
          "routing_correct": true,
          "counterevidence_present": true,
          "safety_pass": true
        },
        {
          "case_id": "policy_conflict_c",
          "context": "conflict_detection",
          "expected_conclusion": "conflicted",
          "observed_conclusion": "conflicted",
          "conclusion_correct": true,
          "expected_focus_strategy": "counterevidence_scan",
          "selected_focus_strategy": "counterevidence_scan",
          "routing_correct": true,
          "counterevidence_present": true,
          "safety_pass": true
        },
        {
          "case_id": "policy_unsupported_a",
          "context": "unsupported_claim",
          "expected_conclusion": "no_support_found_in_stored_memory",
          "observed_conclusion": "no_support_found_in_stored_memory",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_unsupported_b",
          "context": "unsupported_claim",
          "expected_conclusion": "no_support_found_in_stored_memory",
          "observed_conclusion": "no_support_found_in_stored_memory",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        },
        {
          "case_id": "policy_unsupported_c",
          "context": "unsupported_claim",
          "expected_conclusion": "no_support_found_in_stored_memory",
          "observed_conclusion": "no_support_found_in_stored_memory",
          "conclusion_correct": true,
          "expected_focus_strategy": "transitive_graph_search",
          "selected_focus_strategy": "transitive_graph_search",
          "routing_correct": true,
          "counterevidence_present": false,
          "safety_pass": true
        }
      ],
      "epistemic_status": "curated_reference_evaluation_not_external_truth_verification",
      "scope_note": "Suite ini memiliki jalur kode dan fixture terpisah dari training benchmark v0.10. Ia memeriksa perilaku program relatif terhadap label yang ditetapkan sebelumnya; bukan penilai eksternal independen dan bukan bukti kebenaran dunia nyata."
    },
    "strict_routing_improvement": false,
    "conclusion_accuracy_preserved": true,
    "safety_preserved": true,
    "promotion_status": "rejected_or_no_improvement",
    "active": false,
    "source": "user_proposed_policy_mutation",
    "epistemic_status": "curated_holdout_tested_not_externally_validated"
  },
  "promoted": false,
  "active_policy": {
    "direct_relation": "direct_lookup",
    "transitive_inference": "transitive_graph_search",
    "conflict_detection": "counterevidence_scan",
    "unsupported_claim": "transitive_graph_search"
  },
  "holdout_training_ledger_unchanged": true
}
MUTATION> MU00001 status=rejected_or_no_improvement
CATATAN> evaluator deterministik terpisah, bukan evaluator eksternal atau bukti kebenaran dunia nyata.
COGNITIVE_UPDATE> siklus=3; WORKSPACE> strategy_mutation_lab:strategy_policy_mutation_evaluated (0.68), prefrontal_cortex:active_goal (0.60)

KAMU> /mutation-report
{
  "evaluator_id": "cognitive-policy-holdout-v1",
  "active_policy": {
    "direct_relation": "direct_lookup",
    "transitive_inference": "transitive_graph_search",
    "conflict_detection": "counterevidence_scan",
    "unsupported_claim": "transitive_graph_search"
  },
  "active_overrides": {},
  "mutation_count": 1,
  "promoted_count": 0,
  "rejected_or_no_improvement_count": 1,
  "mutations": [
    {
      "mutation_id": "MU00001",
      "mutation_type": "context_focus_override",
      "context": "direct_relation",
      "candidate_strategy": "transitive_graph_search",
      "rationale": "Uji apakah pencarian graf lebih tepat untuk klaim langsung",
      "baseline_policy": {
        "direct_relation": "direct_lookup",
        "transitive_inference": "transitive_graph_search",
        "conflict_detection": "counterevidence_scan",
        "unsupported_claim": "transitive_graph_search"
      },
      "candidate_policy": {
        "direct_relation": "transitive_graph_search",
        "transitive_inference": "transitive_graph_search",
        "conflict_detection": "counterevidence_scan",
        "unsupported_claim": "transitive_graph_search"
      },
      "baseline_evaluation": {
        "evaluator_id": "cognitive-policy-holdout-v1",
        "suite_version": "cognitive-policy-holdout-v1",
        "case_count": 12,
        "conclusion_accuracy": 1.0,
        "routing_accuracy": 1.0,
        "conclusion_cases_correct": 12,
        "routing_cases_correct": 12,
        "safety_pass": true,
        "safety_failures": [],
        "holdout_case_ids": [
          "policy_direct_a",
          "policy_direct_b",
          "policy_direct_c",
          "policy_path_a",
          "policy_path_b",
          "policy_path_c",
          "policy_conflict_a",
          "policy_conflict_b",
          "policy_conflict_c",
          "policy_unsupported_a",
          "policy_unsupported_b",
          "policy_unsupported_c"
        ],
        "training_ledger_write_count": 0,
        "cases": [
          {
            "case_id": "policy_direct_a",
            "context": "direct_relation",
            "expected_conclusion": "direct_assertion_unverified",
            "observed_conclusion": "direct_assertion_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "direct_lookup",
            "selected_focus_strategy": "direct_lookup",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_direct_b",
            "context": "direct_relation",
            "expected_conclusion": "direct_assertion_unverified",
            "observed_conclusion": "direct_assertion_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "direct_lookup",
            "selected_focus_strategy": "direct_lookup",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_direct_c",
            "context": "direct_relation",
            "expected_conclusion": "direct_assertion_unverified",
            "observed_conclusion": "direct_assertion_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "direct_lookup",
            "selected_focus_strategy": "direct_lookup",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_path_a",
            "context": "transitive_inference",
            "expected_conclusion": "inference_path_unverified",
            "observed_conclusion": "inference_path_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_path_b",
            "context": "transitive_inference",
            "expected_conclusion": "inference_path_unverified",
            "observed_conclusion": "inference_path_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_path_c",
            "context": "transitive_inference",
            "expected_conclusion": "inference_path_unverified",
            "observed_conclusion": "inference_path_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_conflict_a",
            "context": "conflict_detection",
            "expected_conclusion": "conflicted",
            "observed_conclusion": "conflicted",
            "conclusion_correct": true,
            "expected_focus_strategy": "counterevidence_scan",
            "selected_focus_strategy": "counterevidence_scan",
            "routing_correct": true,
            "counterevidence_present": true,
            "safety_pass": true
          },
          {
            "case_id": "policy_conflict_b",
            "context": "conflict_detection",
            "expected_conclusion": "conflicted",
            "observed_conclusion": "conflicted",
            "conclusion_correct": true,
            "expected_focus_strategy": "counterevidence_scan",
            "selected_focus_strategy": "counterevidence_scan",
            "routing_correct": true,
            "counterevidence_present": true,
            "safety_pass": true
          },
          {
            "case_id": "policy_conflict_c",
            "context": "conflict_detection",
            "expected_conclusion": "conflicted",
            "observed_conclusion": "conflicted",
            "conclusion_correct": true,
            "expected_focus_strategy": "counterevidence_scan",
            "selected_focus_strategy": "counterevidence_scan",
            "routing_correct": true,
            "counterevidence_present": true,
            "safety_pass": true
          },
          {
            "case_id": "policy_unsupported_a",
            "context": "unsupported_claim",
            "expected_conclusion": "no_support_found_in_stored_memory",
            "observed_conclusion": "no_support_found_in_stored_memory",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_unsupported_b",
            "context": "unsupported_claim",
            "expected_conclusion": "no_support_found_in_stored_memory",
            "observed_conclusion": "no_support_found_in_stored_memory",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_unsupported_c",
            "context": "unsupported_claim",
            "expected_conclusion": "no_support_found_in_stored_memory",
            "observed_conclusion": "no_support_found_in_stored_memory",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          }
        ],
        "epistemic_status": "curated_reference_evaluation_not_external_truth_verification",
        "scope_note": "Suite ini memiliki jalur kode dan fixture terpisah dari training benchmark v0.10. Ia memeriksa perilaku program relatif terhadap label yang ditetapkan sebelumnya; bukan penilai eksternal independen dan bukan bukti kebenaran dunia nyata."
      },
      "candidate_evaluation": {
        "evaluator_id": "cognitive-policy-holdout-v1",
        "suite_version": "cognitive-policy-holdout-v1",
        "case_count": 12,
        "conclusion_accuracy": 1.0,
        "routing_accuracy": 0.75,
        "conclusion_cases_correct": 12,
        "routing_cases_correct": 9,
        "safety_pass": true,
        "safety_failures": [],
        "holdout_case_ids": [
          "policy_direct_a",
          "policy_direct_b",
          "policy_direct_c",
          "policy_path_a",
          "policy_path_b",
          "policy_path_c",
          "policy_conflict_a",
          "policy_conflict_b",
          "policy_conflict_c",
          "policy_unsupported_a",
          "policy_unsupported_b",
          "policy_unsupported_c"
        ],
        "training_ledger_write_count": 0,
        "cases": [
          {
            "case_id": "policy_direct_a",
            "context": "direct_relation",
            "expected_conclusion": "direct_assertion_unverified",
            "observed_conclusion": "direct_assertion_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "direct_lookup",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": false,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_direct_b",
            "context": "direct_relation",
            "expected_conclusion": "direct_assertion_unverified",
            "observed_conclusion": "direct_assertion_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "direct_lookup",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": false,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_direct_c",
            "context": "direct_relation",
            "expected_conclusion": "direct_assertion_unverified",
            "observed_conclusion": "direct_assertion_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "direct_lookup",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": false,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_path_a",
            "context": "transitive_inference",
            "expected_conclusion": "inference_path_unverified",
            "observed_conclusion": "inference_path_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_path_b",
            "context": "transitive_inference",
            "expected_conclusion": "inference_path_unverified",
            "observed_conclusion": "inference_path_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_path_c",
            "context": "transitive_inference",
            "expected_conclusion": "inference_path_unverified",
            "observed_conclusion": "inference_path_unverified",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_conflict_a",
            "context": "conflict_detection",
            "expected_conclusion": "conflicted",
            "observed_conclusion": "conflicted",
            "conclusion_correct": true,
            "expected_focus_strategy": "counterevidence_scan",
            "selected_focus_strategy": "counterevidence_scan",
            "routing_correct": true,
            "counterevidence_present": true,
            "safety_pass": true
          },
          {
            "case_id": "policy_conflict_b",
            "context": "conflict_detection",
            "expected_conclusion": "conflicted",
            "observed_conclusion": "conflicted",
            "conclusion_correct": true,
            "expected_focus_strategy": "counterevidence_scan",
            "selected_focus_strategy": "counterevidence_scan",
            "routing_correct": true,
            "counterevidence_present": true,
            "safety_pass": true
          },
          {
            "case_id": "policy_conflict_c",
            "context": "conflict_detection",
            "expected_conclusion": "conflicted",
            "observed_conclusion": "conflicted",
            "conclusion_correct": true,
            "expected_focus_strategy": "counterevidence_scan",
            "selected_focus_strategy": "counterevidence_scan",
            "routing_correct": true,
            "counterevidence_present": true,
            "safety_pass": true
          },
          {
            "case_id": "policy_unsupported_a",
            "context": "unsupported_claim",
            "expected_conclusion": "no_support_found_in_stored_memory",
            "observed_conclusion": "no_support_found_in_stored_memory",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_unsupported_b",
            "context": "unsupported_claim",
            "expected_conclusion": "no_support_found_in_stored_memory",
            "observed_conclusion": "no_support_found_in_stored_memory",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          },
          {
            "case_id": "policy_unsupported_c",
            "context": "unsupported_claim",
            "expected_conclusion": "no_support_found_in_stored_memory",
            "observed_conclusion": "no_support_found_in_stored_memory",
            "conclusion_correct": true,
            "expected_focus_strategy": "transitive_graph_search",
            "selected_focus_strategy": "transitive_graph_search",
            "routing_correct": true,
            "counterevidence_present": false,
            "safety_pass": true
          }
        ],
        "epistemic_status": "curated_reference_evaluation_not_external_truth_verification",
        "scope_note": "Suite ini memiliki jalur kode dan fixture terpisah dari training benchmark v0.10. Ia memeriksa perilaku program relatif terhadap label yang ditetapkan sebelumnya; bukan penilai eksternal independen dan bukan bukti kebenaran dunia nyata."
      },
      "strict_routing_improvement": false,
      "conclusion_accuracy_preserved": true,
      "safety_preserved": true,
      "promotion_status": "rejected_or_no_improvement",
      "active": false,
      "source": "user_proposed_policy_mutation",
      "epistemic_status": "curated_holdout_tested_not_externally_validated"
    }
  ],
  "scope_note": "Policy aktif hanya berubah setelah kenaikan routing yang ketat, kesimpulan tetap benar pada semua probe, dan invariant konflik lulus."
}

KAMU> /status
{
  "workspace": {
    "cycle": 3,
    "goal": "memahami input dan merespons dengan jujur",
    "arousal": 0.25,
    "learning_rate": 0.2,
    "prediction_error": 0.05,
    "last_action": "propose_strategy_mutation",
    "working_memory_size": 7,
    "broadcast": [
      {
        "source": "strategy_mutation_lab",
        "kind": "strategy_policy_mutation_evaluated",
        "content": {
          "mutation": {
            "mutation_id": "MU00001",
            "mutation_type": "context_focus_override",
            "context": "direct_relation",
            "candidate_strategy": "transitive_graph_search",
            "rationale": "Uji apakah pencarian graf lebih tepat untuk klaim langsung",
            "baseline_policy": {
              "direct_relation": "direct_lookup",
              "transitive_inference": "transitive_graph_search",
              "conflict_detection": "counterevidence_scan",
              "unsupported_claim": "transitive_graph_search"
            },
            "candidate_policy": {
              "direct_relation": "transitive_graph_search",
              "transitive_inference": "transitive_graph_search",
              "conflict_detection": "counterevidence_scan",
              "unsupported_claim": "transitive_graph_search"
            },
            "baseline_evaluation": {
              "evaluator_id": "cognitive-policy-holdout-v1",
              "suite_version": "cognitive-policy-holdout-v1",
              "case_count": 12,
              "conclusion_accuracy": 1.0,
              "routing_accuracy": 1.0,
              "conclusion_cases_correct": 12,
              "routing_cases_correct": 12,
              "safety_pass": true,
              "safety_failures": [],
              "holdout_case_ids": [
                "policy_direct_a",
                "policy_direct_b",
                "policy_direct_c",
                "policy_path_a",
                "policy_path_b",
                "policy_path_c",
                "policy_conflict_a",
                "policy_conflict_b",
                "policy_conflict_c",
                "policy_unsupported_a",
                "policy_unsupported_b",
                "policy_unsupported_c"
              ],
              "training_ledger_write_count": 0,
              "cases": [
                {
                  "case_id": "policy_direct_a",
                  "context": "direct_relation",
                  "expected_conclusion": "direct_assertion_unverified",
                  "observed_conclusion": "direct_assertion_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "direct_lookup",
                  "selected_focus_strategy": "direct_lookup",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_direct_b",
                  "context": "direct_relation",
                  "expected_conclusion": "direct_assertion_unverified",
                  "observed_conclusion": "direct_assertion_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "direct_lookup",
                  "selected_focus_strategy": "direct_lookup",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_direct_c",
                  "context": "direct_relation",
                  "expected_conclusion": "direct_assertion_unverified",
                  "observed_conclusion": "direct_assertion_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "direct_lookup",
                  "selected_focus_strategy": "direct_lookup",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_path_a",
                  "context": "transitive_inference",
                  "expected_conclusion": "inference_path_unverified",
                  "observed_conclusion": "inference_path_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_path_b",
                  "context": "transitive_inference",
                  "expected_conclusion": "inference_path_unverified",
                  "observed_conclusion": "inference_path_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_path_c",
                  "context": "transitive_inference",
                  "expected_conclusion": "inference_path_unverified",
                  "observed_conclusion": "inference_path_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_conflict_a",
                  "context": "conflict_detection",
                  "expected_conclusion": "conflicted",
                  "observed_conclusion": "conflicted",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "counterevidence_scan",
                  "selected_focus_strategy": "counterevidence_scan",
                  "routing_correct": true,
                  "counterevidence_present": true,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_conflict_b",
                  "context": "conflict_detection",
                  "expected_conclusion": "conflicted",
                  "observed_conclusion": "conflicted",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "counterevidence_scan",
                  "selected_focus_strategy": "counterevidence_scan",
                  "routing_correct": true,
                  "counterevidence_present": true,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_conflict_c",
                  "context": "conflict_detection",
                  "expected_conclusion": "conflicted",
                  "observed_conclusion": "conflicted",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "counterevidence_scan",
                  "selected_focus_strategy": "counterevidence_scan",
                  "routing_correct": true,
                  "counterevidence_present": true,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_unsupported_a",
                  "context": "unsupported_claim",
                  "expected_conclusion": "no_support_found_in_stored_memory",
                  "observed_conclusion": "no_support_found_in_stored_memory",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_unsupported_b",
                  "context": "unsupported_claim",
                  "expected_conclusion": "no_support_found_in_stored_memory",
                  "observed_conclusion": "no_support_found_in_stored_memory",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_unsupported_c",
                  "context": "unsupported_claim",
                  "expected_conclusion": "no_support_found_in_stored_memory",
                  "observed_conclusion": "no_support_found_in_stored_memory",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                }
              ],
              "epistemic_status": "curated_reference_evaluation_not_external_truth_verification",
              "scope_note": "Suite ini memiliki jalur kode dan fixture terpisah dari training benchmark v0.10. Ia memeriksa perilaku program relatif terhadap label yang ditetapkan sebelumnya; bukan penilai eksternal independen dan bukan bukti kebenaran dunia nyata."
            },
            "candidate_evaluation": {
              "evaluator_id": "cognitive-policy-holdout-v1",
              "suite_version": "cognitive-policy-holdout-v1",
              "case_count": 12,
              "conclusion_accuracy": 1.0,
              "routing_accuracy": 0.75,
              "conclusion_cases_correct": 12,
              "routing_cases_correct": 9,
              "safety_pass": true,
              "safety_failures": [],
              "holdout_case_ids": [
                "policy_direct_a",
                "policy_direct_b",
                "policy_direct_c",
                "policy_path_a",
                "policy_path_b",
                "policy_path_c",
                "policy_conflict_a",
                "policy_conflict_b",
                "policy_conflict_c",
                "policy_unsupported_a",
                "policy_unsupported_b",
                "policy_unsupported_c"
              ],
              "training_ledger_write_count": 0,
              "cases": [
                {
                  "case_id": "policy_direct_a",
                  "context": "direct_relation",
                  "expected_conclusion": "direct_assertion_unverified",
                  "observed_conclusion": "direct_assertion_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "direct_lookup",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": false,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_direct_b",
                  "context": "direct_relation",
                  "expected_conclusion": "direct_assertion_unverified",
                  "observed_conclusion": "direct_assertion_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "direct_lookup",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": false,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_direct_c",
                  "context": "direct_relation",
                  "expected_conclusion": "direct_assertion_unverified",
                  "observed_conclusion": "direct_assertion_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "direct_lookup",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": false,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_path_a",
                  "context": "transitive_inference",
                  "expected_conclusion": "inference_path_unverified",
                  "observed_conclusion": "inference_path_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_path_b",
                  "context": "transitive_inference",
                  "expected_conclusion": "inference_path_unverified",
                  "observed_conclusion": "inference_path_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_path_c",
                  "context": "transitive_inference",
                  "expected_conclusion": "inference_path_unverified",
                  "observed_conclusion": "inference_path_unverified",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_conflict_a",
                  "context": "conflict_detection",
                  "expected_conclusion": "conflicted",
                  "observed_conclusion": "conflicted",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "counterevidence_scan",
                  "selected_focus_strategy": "counterevidence_scan",
                  "routing_correct": true,
                  "counterevidence_present": true,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_conflict_b",
                  "context": "conflict_detection",
                  "expected_conclusion": "conflicted",
                  "observed_conclusion": "conflicted",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "counterevidence_scan",
                  "selected_focus_strategy": "counterevidence_scan",
                  "routing_correct": true,
                  "counterevidence_present": true,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_conflict_c",
                  "context": "conflict_detection",
                  "expected_conclusion": "conflicted",
                  "observed_conclusion": "conflicted",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "counterevidence_scan",
                  "selected_focus_strategy": "counterevidence_scan",
                  "routing_correct": true,
                  "counterevidence_present": true,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_unsupported_a",
                  "context": "unsupported_claim",
                  "expected_conclusion": "no_support_found_in_stored_memory",
                  "observed_conclusion": "no_support_found_in_stored_memory",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_unsupported_b",
                  "context": "unsupported_claim",
                  "expected_conclusion": "no_support_found_in_stored_memory",
                  "observed_conclusion": "no_support_found_in_stored_memory",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                },
                {
                  "case_id": "policy_unsupported_c",
                  "context": "unsupported_claim",
                  "expected_conclusion": "no_support_found_in_stored_memory",
                  "observed_conclusion": "no_support_found_in_stored_memory",
                  "conclusion_correct": true,
                  "expected_focus_strategy": "transitive_graph_search",
                  "selected_focus_strategy": "transitive_graph_search",
                  "routing_correct": true,
                  "counterevidence_present": false,
                  "safety_pass": true
                }
              ],
              "epistemic_status": "curated_reference_evaluation_not_external_truth_verification",
              "scope_note": "Suite ini memiliki jalur kode dan fixture terpisah dari training benchmark v0.10. Ia memeriksa perilaku program relatif terhadap label yang ditetapkan sebelumnya; bukan penilai eksternal independen dan bukan bukti kebenaran dunia nyata."
            },
            "strict_routing_improvement": false,
            "conclusion_accuracy_preserved": true,
            "safety_preserved": true,
            "promotion_status": "rejected_or_no_improvement",
            "active": false,
            "source": "user_proposed_policy_mutation",
            "epistemic_status": "curated_holdout_tested_not_externally_validated"
          }
        },
        "confidence": 0.95,
        "novelty": 0.6,
        "urgency": 0.0,
        "goal_relevance": 0.95,
        "evidence": [
          "perubahan atau rencana berasal dari perintah eksplisit pengguna"
        ],
        "score": 0.6761999999999999
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
        "score": 0.6027
      }
    ]
  },
  "cognitive_cycles_this_run": 3,
  "cognitive_cycles_total": 3,
  "episodic_memories": 3,
  "semantic_relations": 1,
  "hypotheses": 0,
  "hypothesis_evidence_records": 0,
  "provenance_claims": 0,
  "provenance_evidence_records": 0,
  "provenance_external_checks": 0,
  "memory_schema_version": 10,
  "feedback_count": 0,
  "average_reward": null,
  "action_values": {},
  "strategy_learning": {},
  "strategy_applicability_learning": {},
  "strategy_benchmark_training_trials": 0,
  "strategy_declared_outcomes": 0,
  "failure_diagnoses": 0,
  "reusable_strategy_lessons": 0,
  "strategy_mutations": 1,
  "active_strategy_policy_overrides": {},
  "unresolved_contradictions": [],
  "event_count_this_run": 33,
  "needs": {
    "energy": 0.995,
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
    "independent_verifier",
    "multi_strategy_reasoner",
    "global_workspace"
  ],
  "llm_used": false
}

KAMU> quit
Memori disimpan. Sampai jumpa.

putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python -m brain_ai.cli --memory migration_copy.json
Human-Inspired Cognitive AI v0.11.0 — tanpa LLM
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
Bahasa sederhana: kucing adalah mamalia; jika hujan maka jalan basah; hipotesis tentang cuaca?

KAMU> quit
Memori disimpan. Sampai jumpa.
