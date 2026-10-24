              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0005",
              "split": "validation",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0006",
              "split": "validation",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0007",
              "split": "validation",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0008",
              "split": "validation",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0009",
              "split": "validation",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0010",
              "split": "validation",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0011",
              "split": "validation",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0012",
              "split": "validation",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0013",
              "split": "validation",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0014",
              "split": "validation",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0015",
              "split": "validation",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0016",
              "split": "validation",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0017",
              "split": "validation",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0018",
              "split": "validation",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "candidate_selected_on_validation": false,
        "selected_policy": {
          "target_conflict": [
            "counterevidence_scan",
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier"
          ],
          "path_conflict": [
            "transitive_graph_search",
            "counterevidence_scan",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "multi_scope_conflict": [
            "counterevidence_scan",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "direct_branching": [
            "transitive_graph_search",
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ],
          "transitive_branching": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "direct_only": [
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan",
            "transitive_graph_search"
          ],
          "transitive_deep": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "transitive_shallow": [
            "transitive_graph_search",
            "direct_lookup",
            "counterevidence_scan",
            "independent_integrity_verifier"
          ],
          "unsupported": [
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ]
        },
        "holdout_baseline": {
          "case_count": 18,
          "order_matches": 18,
          "order_accuracy": 1.0,
          "profile_matches": 18,
          "profile_accuracy": 1.0,
          "oracle_matches": 18,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 18,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 18,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXH0001",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0002",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0003",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0004",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0005",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0006",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0007",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0008",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0009",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0010",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0011",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0012",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0013",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0014",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0015",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0016",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0017",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0018",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "holdout_candidate": {
          "case_count": 18,
          "order_matches": 18,
          "order_accuracy": 1.0,
          "profile_matches": 18,
          "profile_accuracy": 1.0,
          "oracle_matches": 18,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 18,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 18,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXH0001",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0002",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0003",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0004",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0005",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0006",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0007",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0008",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0009",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0010",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0011",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0012",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0013",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0014",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0015",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0016",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0017",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0018",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "open_world_generalization": {
          "suite_version": "open-world-compositional-audit-v1",
          "status": "PASS",
          "seed": 324532640,
          "generator": "factorized_random_graph_compositions_without_expected_orders_or_profile_labels",
          "training_profile_labels_provided_to_evaluator": false,
          "expected_strategy_orders_provided": false,
          "challenge_count": 18,
          "candidate": {
            "case_count": 18,
            "oracle_matches": 18,
            "oracle_match_rate": 1.0,
            "structural_constraint_passes": 18,
            "structural_constraint_pass_rate": 1.0,
            "structural_constraint_violation_count": 0,
            "conflict_priority_passes": 18,
            "conflict_priority_pass_rate": 1.0,
            "conflicted_cases": 3,
            "mean_position_discounted_utility": 0.77476,
            "inferred_profile_distribution": {
              "direct_branching": 3,
              "direct_only": 1,
              "target_conflict": 3,
              "transitive_branching": 5,
              "transitive_deep": 2,
              "transitive_shallow": 1,
              "unsupported": 3
            },
            "conflict_scope_distribution": {
              "no_conflict": 15,
              "target": 3
            },
            "passed": true,
            "rows": [
              {
                "case_id": "OW0001",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0002",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0003",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0004",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": true,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0005",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0006",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0007",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0008",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0009",
                "inferred_profile": "transitive_deep",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 40.0,
                  "transitive_graph_search": 115.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.807292,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": true,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0010",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0011",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0012",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0013",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0014",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0015",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0016",
                "inferred_profile": "transitive_shallow",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "counterevidence_scan",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 2,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 65.0,
                  "transitive_graph_search": 105.0,
                  "counterevidence_scan": 25.0,
                  "independent_integrity_verifier": 15.0
                },
                "position_discounted_utility": 0.809524,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0017",
                "inferred_profile": "transitive_deep",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 40.0,
                  "transitive_graph_search": 110.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.803191,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": true,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0018",
                "inferred_profile": "direct_only",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan",
                  "transitive_graph_search"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 2,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 100.0,
                  "transitive_graph_search": 5.0,
                  "counterevidence_scan": 15.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.846154,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              }
            ]
          },
          "baseline": {
            "case_count": 18,
            "oracle_matches": 18,
            "oracle_match_rate": 1.0,
            "structural_constraint_passes": 18,
            "structural_constraint_pass_rate": 1.0,
            "structural_constraint_violation_count": 0,
            "conflict_priority_passes": 18,
            "conflict_priority_pass_rate": 1.0,
            "conflicted_cases": 3,
            "mean_position_discounted_utility": 0.77476,
            "inferred_profile_distribution": {
              "direct_branching": 3,
              "direct_only": 1,
              "target_conflict": 3,
              "transitive_branching": 5,
              "transitive_deep": 2,
              "transitive_shallow": 1,
              "unsupported": 3
            },
            "conflict_scope_distribution": {
              "no_conflict": 15,
              "target": 3
            },
            "passed": true,
            "rows": [
              {
                "case_id": "OW0001",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0002",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0003",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0004",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": true,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0005",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0006",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0007",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0008",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0009",
                "inferred_profile": "transitive_deep",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 40.0,
                  "transitive_graph_search": 115.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.807292,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": true,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0010",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0011",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0012",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0013",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0014",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0015",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0016",
                "inferred_profile": "transitive_shallow",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "counterevidence_scan",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 2,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 65.0,
                  "transitive_graph_search": 105.0,
                  "counterevidence_scan": 25.0,
                  "independent_integrity_verifier": 15.0
                },
                "position_discounted_utility": 0.809524,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0017",
                "inferred_profile": "transitive_deep",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 40.0,
                  "transitive_graph_search": 110.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.803191,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": true,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0018",
                "inferred_profile": "direct_only",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan",
                  "transitive_graph_search"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 2,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 100.0,
                  "transitive_graph_search": 5.0,
                  "counterevidence_scan": 15.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.846154,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              }
            ]
          },
          "candidate_minus_baseline_utility": 0.0,
          "robustness_passed": true,
          "utility_improved": false,
          "promotion_gate_passed": false,
          "interpretation_limit": "Generalization is tested on generated graph compositions not assigned training profile labels; oracle and constraints remain internal graph semantics, not external factual truth."
        },
        "promotion_accepted": false,
        "promotion_status": "not_promoted",
        "active_policy_changed": false,
        "active_policy_after": {
          "target_conflict": [
            "counterevidence_scan",
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier"
          ],
          "path_conflict": [
            "transitive_graph_search",
            "counterevidence_scan",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "multi_scope_conflict": [
            "counterevidence_scan",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "direct_branching": [
            "transitive_graph_search",
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ],
          "transitive_branching": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "direct_only": [
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan",
            "transitive_graph_search"
          ],
          "transitive_deep": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "transitive_shallow": [
            "transitive_graph_search",
            "direct_lookup",
            "counterevidence_scan",
            "independent_integrity_verifier"
          ],
          "unsupported": [
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ]
        },
        "isolation_invariants": {
          "case_ids_pairwise_disjoint": true,
          "entity_namespaces_pairwise_disjoint": true,
          "holdout_not_used_for_candidate_selection": true,
          "holdout_not_used_for_training_policy": true,
          "holdout_does_not_change_training_support": true,
          "open_world_cases_have_no_profile_or_expected_order_labels": true,
          "open_world_only_gates_promotion_not_candidate_order": true,
          "open_world_oracle_match_rate_is_perfect": true,
          "open_world_structural_constraints_all_pass": true,
          "all_profiles_have_safe_complete_order": true,
          "holdout_reasoner_verdicts_match_oracle": true,
          "holdout_profile_extraction_correct": true
        },
        "isolation_passed": true,
        "training_case_ids": [
          "CXT0001",
          "CXT0002",
          "CXT0003",
          "CXT0004",
          "CXT0005",
          "CXT0006",
          "CXT0007",
          "CXT0008",
          "CXT0009",
          "CXT0010",
          "CXT0011",
          "CXT0012",
          "CXT0013",
          "CXT0014",
          "CXT0015",
          "CXT0016",
          "CXT0017",
          "CXT0018",
          "CXT0019",
          "CXT0020",
          "CXT0021",
          "CXT0022",
          "CXT0023",
          "CXT0024",
          "CXT0025",
          "CXT0026",
          "CXT0027",
          "CXT0028",
          "CXT0029",
          "CXT0030",
          "CXT0031",
          "CXT0032",
          "CXT0033",
          "CXT0034",
          "CXT0035",
          "CXT0036"
        ],
        "validation_case_ids": [
          "CXV0001",
          "CXV0002",
          "CXV0003",
          "CXV0004",
          "CXV0005",
          "CXV0006",
          "CXV0007",
          "CXV0008",
          "CXV0009",
          "CXV0010",
          "CXV0011",
          "CXV0012",
          "CXV0013",
          "CXV0014",
          "CXV0015",
          "CXV0016",
          "CXV0017",
          "CXV0018"
        ],
        "holdout_case_ids": [
          "CXH0001",
          "CXH0002",
          "CXH0003",
          "CXH0004",
          "CXH0005",
          "CXH0006",
          "CXH0007",
          "CXH0008",
          "CXH0009",
          "CXH0010",
          "CXH0011",
          "CXH0012",
          "CXH0013",
          "CXH0014",
          "CXH0015",
          "CXH0016",
          "CXH0017",
          "CXH0018"
        ],
        "training_profile_set": [
          "direct_branching",
          "direct_only",
          "multi_scope_conflict",
          "path_conflict",
          "target_conflict",
          "transitive_branching",
          "transitive_deep",
          "transitive_shallow",
          "unsupported"
        ],
        "validation_profile_set": [
          "direct_branching",
          "direct_only",
          "multi_scope_conflict",
          "path_conflict",
          "target_conflict",
          "transitive_branching",
          "transitive_deep",
          "transitive_shallow",
          "unsupported"
        ],
        "holdout_profile_set": [
          "direct_branching",
          "direct_only",
          "multi_scope_conflict",
          "path_conflict",
          "target_conflict",
          "transitive_branching",
          "transitive_deep",
          "transitive_shallow",
          "unsupported"
        ],
        "candidate_policy_source": "observed_reasoner_evidence_priority_scores",
        "open_world_promotion_gate_passed": false,
        "fixture_expected_orders_used_for_candidate_selection": false,
        "independent_evaluator": "observed_evidence_constraints_plus_position_discounted_relevance_and_unlabelled_open_world_compositions",
        "records_facts_changed": false,
        "records_training_ledger_changed": false,
        "records_user_outcomes_changed": false,
        "epistemic_limit": "Kebijakan diturunkan dari output reasoner; evaluasi tetap memakai graf sintetis dan oracle internal, bukan bukti kebenaran eksternal."
      }
    },
    "independent_seed": {
      "promotion_accepted": false,
      "promotion_status": "not_promoted",
      "safety_passed": true,
      "utility_gains": {
        "validation": 0.0,
        "holdout": 0.0,
        "open_world": 0.0
      },
      "report": {
        "suite_version": "open-world-gated-context-composition-v3",
        "status": "PASS",
        "seed": 1024004,
        "train_case_count": 36,
        "validation_case_count": 18,
        "holdout_case_count": 18,
        "active_policy_before": {
          "target_conflict": [
            "counterevidence_scan",
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier"
          ],
          "path_conflict": [
            "transitive_graph_search",
            "counterevidence_scan",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "multi_scope_conflict": [
            "counterevidence_scan",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "direct_branching": [
            "transitive_graph_search",
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ],
          "transitive_branching": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "direct_only": [
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan",
            "transitive_graph_search"
          ],
          "transitive_deep": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "transitive_shallow": [
            "transitive_graph_search",
            "direct_lookup",
            "counterevidence_scan",
            "independent_integrity_verifier"
          ],
          "unsupported": [
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ]
        },
        "training_baseline": {
          "case_count": 36,
          "order_matches": 36,
          "order_accuracy": 1.0,
          "profile_matches": 36,
          "profile_accuracy": 1.0,
          "oracle_matches": 36,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 36,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 36,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXT0001",
              "split": "training",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0002",
              "split": "training",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0003",
              "split": "training",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0004",
              "split": "training",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0005",
              "split": "training",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0006",
              "split": "training",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0007",
              "split": "training",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0008",
              "split": "training",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0009",
              "split": "training",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0010",
              "split": "training",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0011",
              "split": "training",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0012",
              "split": "training",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0013",
              "split": "training",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0014",
              "split": "training",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0015",
              "split": "training",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0016",
              "split": "training",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0017",
              "split": "training",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0018",
              "split": "training",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0019",
              "split": "training",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0020",
              "split": "training",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0021",
              "split": "training",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0022",
              "split": "training",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0023",
              "split": "training",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0024",
              "split": "training",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0025",
              "split": "training",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0026",
              "split": "training",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0027",
              "split": "training",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0028",
              "split": "training",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0029",
              "split": "training",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0030",
              "split": "training",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0031",
              "split": "training",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0032",
              "split": "training",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0033",
              "split": "training",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0034",
              "split": "training",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0035",
              "split": "training",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXT0036",
              "split": "training",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "training_learning": {
          "training_support_by_profile": {
            "target_conflict": 4,
            "path_conflict": 4,
            "multi_scope_conflict": 4,
            "direct_branching": 4,
            "transitive_branching": 4,
            "direct_only": 4,
            "transitive_deep": 4,
            "transitive_shallow": 4,
            "unsupported": 4
          },
          "candidate_source": "observed_reasoner_evidence_priority_scores",
          "fixture_expected_orders_used_for_candidate_selection": false,
          "mean_priority_scores_by_profile": {
            "target_conflict": {
              "direct_lookup": 85.0,
              "transitive_graph_search": 60.0,
              "counterevidence_scan": 100.0,
              "independent_integrity_verifier": 45.0
            },
            "path_conflict": {
              "direct_lookup": 20.0,
              "transitive_graph_search": 100.0,
              "counterevidence_scan": 90.0,
              "independent_integrity_verifier": 75.0
            },
            "multi_scope_conflict": {
              "direct_lookup": 30.0,
              "transitive_graph_search": 95.0,
              "counterevidence_scan": 100.0,
              "independent_integrity_verifier": 80.0
            },
            "direct_branching": {
              "direct_lookup": 85.0,
              "transitive_graph_search": 100.0,
              "counterevidence_scan": 10.0,
              "independent_integrity_verifier": 60.0
            },
            "transitive_branching": {
              "direct_lookup": 35.0,
              "transitive_graph_search": 100.0,
              "counterevidence_scan": 10.0,
              "independent_integrity_verifier": 80.0
            },
            "direct_only": {
              "direct_lookup": 100.0,
              "transitive_graph_search": 5.0,
              "counterevidence_scan": 15.0,
              "independent_integrity_verifier": 75.0
            },
            "transitive_deep": {
              "direct_lookup": 40.0,
              "transitive_graph_search": 115.0,
              "counterevidence_scan": 10.0,
              "independent_integrity_verifier": 75.0
            },
            "transitive_shallow": {
              "direct_lookup": 65.0,
              "transitive_graph_search": 105.0,
              "counterevidence_scan": 25.0,
              "independent_integrity_verifier": 15.0
            },
            "unsupported": {
              "direct_lookup": 75.0,
              "transitive_graph_search": 65.0,
              "counterevidence_scan": 10.0,
              "independent_integrity_verifier": 55.0
            }
          }
        },
        "validation_baseline": {
          "case_count": 18,
          "order_matches": 18,
          "order_accuracy": 1.0,
          "profile_matches": 18,
          "profile_accuracy": 1.0,
          "oracle_matches": 18,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 18,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 18,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXV0001",
              "split": "validation",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0002",
              "split": "validation",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0003",
              "split": "validation",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0004",
              "split": "validation",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0005",
              "split": "validation",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0006",
              "split": "validation",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0007",
              "split": "validation",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0008",
              "split": "validation",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0009",
              "split": "validation",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0010",
              "split": "validation",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0011",
              "split": "validation",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0012",
              "split": "validation",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0013",
              "split": "validation",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0014",
              "split": "validation",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0015",
              "split": "validation",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0016",
              "split": "validation",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0017",
              "split": "validation",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0018",
              "split": "validation",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "validation_candidate": {
          "case_count": 18,
          "order_matches": 18,
          "order_accuracy": 1.0,
          "profile_matches": 18,
          "profile_accuracy": 1.0,
          "oracle_matches": 18,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 18,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 18,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXV0001",
              "split": "validation",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0002",
              "split": "validation",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0003",
              "split": "validation",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0004",
              "split": "validation",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0005",
              "split": "validation",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0006",
              "split": "validation",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0007",
              "split": "validation",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0008",
              "split": "validation",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0009",
              "split": "validation",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0010",
              "split": "validation",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0011",
              "split": "validation",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0012",
              "split": "validation",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0013",
              "split": "validation",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0014",
              "split": "validation",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0015",
              "split": "validation",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0016",
              "split": "validation",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0017",
              "split": "validation",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXV0018",
              "split": "validation",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "candidate_selected_on_validation": false,
        "selected_policy": {
          "target_conflict": [
            "counterevidence_scan",
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier"
          ],
          "path_conflict": [
            "transitive_graph_search",
            "counterevidence_scan",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "multi_scope_conflict": [
            "counterevidence_scan",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "direct_branching": [
            "transitive_graph_search",
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ],
          "transitive_branching": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "direct_only": [
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan",
            "transitive_graph_search"
          ],
          "transitive_deep": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "transitive_shallow": [
            "transitive_graph_search",
            "direct_lookup",
            "counterevidence_scan",
            "independent_integrity_verifier"
          ],
          "unsupported": [
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ]
        },
        "holdout_baseline": {
          "case_count": 18,
          "order_matches": 18,
          "order_accuracy": 1.0,
          "profile_matches": 18,
          "profile_accuracy": 1.0,
          "oracle_matches": 18,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 18,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 18,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXH0001",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0002",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0003",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0004",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0005",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0006",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0007",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0008",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0009",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0010",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0011",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0012",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0013",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0014",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0015",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0016",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0017",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0018",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "holdout_candidate": {
          "case_count": 18,
          "order_matches": 18,
          "order_accuracy": 1.0,
          "profile_matches": 18,
          "profile_accuracy": 1.0,
          "oracle_matches": 18,
          "oracle_match_rate": 1.0,
          "safe": true,
          "missed_conflict_priority": 0,
          "independent_structural_utility": 0.771503,
          "independent_best_order_matches": 18,
          "independent_evaluator_match_rate": 1.0,
          "independent_evaluator_pass": true,
          "structural_constraint_passes": 18,
          "structural_constraint_violations": 0,
          "structural_constraint_pass_rate": 1.0,
          "rows": [
            {
              "case_id": "CXH0001",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0002",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0003",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0004",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0005",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0006",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0007",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0008",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0009",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0010",
              "split": "holdout",
              "profile": "target_conflict",
              "observed_profile": "target_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 60.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 45.0
              },
              "independent_utility": 0.706897,
              "independent_best_order": [
                "counterevidence_scan",
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0011",
              "split": "holdout",
              "profile": "path_conflict",
              "observed_profile": "path_conflict",
              "profile_match": true,
              "observed_status": "inference_path_conflicted",
              "oracle_status": "inference_path_conflicted",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 1,
              "priority_scores": {
                "direct_lookup": 20.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 90.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.736842,
              "independent_best_order": [
                "transitive_graph_search",
                "counterevidence_scan",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0012",
              "split": "holdout",
              "profile": "multi_scope_conflict",
              "observed_profile": "multi_scope_conflict",
              "profile_match": true,
              "observed_status": "conflicted",
              "oracle_status": "conflicted",
              "oracle_match": true,
              "policy_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "expected_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 0,
              "priority_scores": {
                "direct_lookup": 30.0,
                "transitive_graph_search": 95.0,
                "counterevidence_scan": 100.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.717213,
              "independent_best_order": [
                "counterevidence_scan",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0013",
              "split": "holdout",
              "profile": "direct_branching",
              "observed_profile": "direct_branching",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 85.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 60.0
              },
              "independent_utility": 0.769608,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0014",
              "split": "holdout",
              "profile": "transitive_branching",
              "observed_profile": "transitive_branching",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 35.0,
                "transitive_graph_search": 100.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 80.0
              },
              "independent_utility": 0.8,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0015",
              "split": "holdout",
              "profile": "direct_only",
              "observed_profile": "direct_only",
              "profile_match": true,
              "observed_status": "direct_assertion_unverified",
              "oracle_status": "direct_assertion_unverified",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "expected_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 100.0,
                "transitive_graph_search": 5.0,
                "counterevidence_scan": 15.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.846154,
              "independent_best_order": [
                "direct_lookup",
                "independent_integrity_verifier",
                "counterevidence_scan",
                "transitive_graph_search"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0016",
              "split": "holdout",
              "profile": "transitive_deep",
              "observed_profile": "transitive_deep",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "expected_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 40.0,
                "transitive_graph_search": 115.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 75.0
              },
              "independent_utility": 0.807292,
              "independent_best_order": [
                "transitive_graph_search",
                "independent_integrity_verifier",
                "direct_lookup",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0017",
              "split": "holdout",
              "profile": "transitive_shallow",
              "observed_profile": "transitive_shallow",
              "profile_match": true,
              "observed_status": "inference_path_unverified",
              "oracle_status": "inference_path_unverified",
              "oracle_match": true,
              "policy_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "expected_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 2,
              "priority_scores": {
                "direct_lookup": 65.0,
                "transitive_graph_search": 105.0,
                "counterevidence_scan": 25.0,
                "independent_integrity_verifier": 15.0
              },
              "independent_utility": 0.809524,
              "independent_best_order": [
                "transitive_graph_search",
                "direct_lookup",
                "counterevidence_scan",
                "independent_integrity_verifier"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            },
            {
              "case_id": "CXH0018",
              "split": "holdout",
              "profile": "unsupported",
              "observed_profile": "unsupported",
              "profile_match": true,
              "observed_status": "no_support_found_in_stored_memory",
              "oracle_status": "no_support_found_in_stored_memory",
              "oracle_match": true,
              "policy_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "expected_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "order_match": true,
              "safe": true,
              "counterevidence_position": 3,
              "priority_scores": {
                "direct_lookup": 75.0,
                "transitive_graph_search": 65.0,
                "counterevidence_scan": 10.0,
                "independent_integrity_verifier": 55.0
              },
              "independent_utility": 0.75,
              "independent_best_order": [
                "direct_lookup",
                "transitive_graph_search",
                "independent_integrity_verifier",
                "counterevidence_scan"
              ],
              "structural_constraint_pass": true,
              "structural_constraint_violations": []
            }
          ]
        },
        "open_world_generalization": {
          "suite_version": "open-world-compositional-audit-v1",
          "status": "PASS",
          "seed": 325532643,
          "generator": "factorized_random_graph_compositions_without_expected_orders_or_profile_labels",
          "training_profile_labels_provided_to_evaluator": false,
          "expected_strategy_orders_provided": false,
          "challenge_count": 18,
          "candidate": {
            "case_count": 18,
            "oracle_matches": 18,
            "oracle_match_rate": 1.0,
            "structural_constraint_passes": 18,
            "structural_constraint_pass_rate": 1.0,
            "structural_constraint_violation_count": 0,
            "conflict_priority_passes": 18,
            "conflict_priority_pass_rate": 1.0,
            "conflicted_cases": 6,
            "mean_position_discounted_utility": 0.765012,
            "inferred_profile_distribution": {
              "direct_branching": 1,
              "direct_only": 1,
              "path_conflict": 2,
              "target_conflict": 4,
              "transitive_branching": 6,
              "transitive_deep": 1,
              "unsupported": 3
            },
            "conflict_scope_distribution": {
              "inference_path_edge": 2,
              "no_conflict": 12,
              "target": 4
            },
            "passed": true,
            "rows": [
              {
                "case_id": "OW0001",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0002",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0003",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0004",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0005",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0006",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0007",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0008",
                "inferred_profile": "path_conflict",
                "conclusion_status": "direct_assertion_unverified_with_conflicted_path",
                "oracle_status": "direct_assertion_unverified_with_conflicted_path",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "counterevidence_scan",
                  "independent_integrity_verifier",
                  "direct_lookup"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "inference_path_edge"
                ],
                "conflict_detected": true,
                "counterevidence_position": 1,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 20.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 90.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.736842,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": true
                }
              },
              {
                "case_id": "OW0009",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0010",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0011",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0012",
                "inferred_profile": "transitive_deep",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 40.0,
                  "transitive_graph_search": 110.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.803191,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0013",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0014",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0015",
                "inferred_profile": "path_conflict",
                "conclusion_status": "inference_path_conflicted",
                "oracle_status": "inference_path_conflicted",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "counterevidence_scan",
                  "independent_integrity_verifier",
                  "direct_lookup"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "inference_path_edge"
                ],
                "conflict_detected": true,
                "counterevidence_position": 1,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 20.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 90.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.736842,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": true
                }
              },
              {
                "case_id": "OW0016",
                "inferred_profile": "direct_only",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan",
                  "transitive_graph_search"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 2,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 100.0,
                  "transitive_graph_search": 5.0,
                  "counterevidence_scan": 15.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.846154,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0017",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0018",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              }
            ]
          },
          "baseline": {
            "case_count": 18,
            "oracle_matches": 18,
            "oracle_match_rate": 1.0,
            "structural_constraint_passes": 18,
            "structural_constraint_pass_rate": 1.0,
            "structural_constraint_violation_count": 0,
            "conflict_priority_passes": 18,
            "conflict_priority_pass_rate": 1.0,
            "conflicted_cases": 6,
            "mean_position_discounted_utility": 0.765012,
            "inferred_profile_distribution": {
              "direct_branching": 1,
              "direct_only": 1,
              "path_conflict": 2,
              "target_conflict": 4,
              "transitive_branching": 6,
              "transitive_deep": 1,
              "unsupported": 3
            },
            "conflict_scope_distribution": {
              "inference_path_edge": 2,
              "no_conflict": 12,
              "target": 4
            },
            "passed": true,
            "rows": [
              {
                "case_id": "OW0001",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0002",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0003",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0004",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0005",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0006",
                "inferred_profile": "direct_branching",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 60.0
                },
                "position_discounted_utility": 0.769608,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0007",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0008",
                "inferred_profile": "path_conflict",
                "conclusion_status": "direct_assertion_unverified_with_conflicted_path",
                "oracle_status": "direct_assertion_unverified_with_conflicted_path",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "counterevidence_scan",
                  "independent_integrity_verifier",
                  "direct_lookup"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "inference_path_edge"
                ],
                "conflict_detected": true,
                "counterevidence_position": 1,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 20.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 90.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.736842,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": true
                }
              },
              {
                "case_id": "OW0009",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0010",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 3,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0011",
                "inferred_profile": "unsupported",
                "conclusion_status": "no_support_found_in_stored_memory",
                "oracle_status": "no_support_found_in_stored_memory",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 75.0,
                  "transitive_graph_search": 65.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 55.0
                },
                "position_discounted_utility": 0.75,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0012",
                "inferred_profile": "transitive_deep",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 40.0,
                  "transitive_graph_search": 110.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.803191,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0013",
                "inferred_profile": "transitive_branching",
                "conclusion_status": "inference_path_unverified",
                "oracle_status": "inference_path_unverified",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "independent_integrity_verifier",
                  "direct_lookup",
                  "counterevidence_scan"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 3,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 35.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 10.0,
                  "independent_integrity_verifier": 80.0
                },
                "position_discounted_utility": 0.8,
                "generator_features": {
                  "route_seeded": 2,
                  "shared_prefix_requested": true,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0014",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0015",
                "inferred_profile": "path_conflict",
                "conclusion_status": "inference_path_conflicted",
                "oracle_status": "inference_path_conflicted",
                "oracle_match": true,
                "policy_order": [
                  "transitive_graph_search",
                  "counterevidence_scan",
                  "independent_integrity_verifier",
                  "direct_lookup"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "inference_path_edge"
                ],
                "conflict_detected": true,
                "counterevidence_position": 1,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 20.0,
                  "transitive_graph_search": 100.0,
                  "counterevidence_scan": 90.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.736842,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": false,
                  "path_negative_requested": true
                }
              },
              {
                "case_id": "OW0016",
                "inferred_profile": "direct_only",
                "conclusion_status": "direct_assertion_unverified",
                "oracle_status": "direct_assertion_unverified",
                "oracle_match": true,
                "policy_order": [
                  "direct_lookup",
                  "independent_integrity_verifier",
                  "counterevidence_scan",
                  "transitive_graph_search"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [],
                "conflict_detected": false,
                "counterevidence_position": 2,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 100.0,
                  "transitive_graph_search": 5.0,
                  "counterevidence_scan": 15.0,
                  "independent_integrity_verifier": 75.0
                },
                "position_discounted_utility": 0.846154,
                "generator_features": {
                  "route_seeded": 0,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": false,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0017",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": false,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              },
              {
                "case_id": "OW0018",
                "inferred_profile": "target_conflict",
                "conclusion_status": "conflicted",
                "oracle_status": "conflicted",
                "oracle_match": true,
                "policy_order": [
                  "counterevidence_scan",
                  "direct_lookup",
                  "transitive_graph_search",
                  "independent_integrity_verifier"
                ],
                "structural_audit_pass": true,
                "structural_violations": [],
                "counterevidence_scopes": [
                  "target"
                ],
                "conflict_detected": true,
                "counterevidence_position": 0,
                "conflict_priority_pass": true,
                "evidence_priority_scores": {
                  "direct_lookup": 85.0,
                  "transitive_graph_search": 60.0,
                  "counterevidence_scan": 100.0,
                  "independent_integrity_verifier": 45.0
                },
                "position_discounted_utility": 0.706897,
                "generator_features": {
                  "route_seeded": 1,
                  "shared_prefix_requested": false,
                  "shared_suffix_requested": false,
                  "direct_shortcut_requested": true,
                  "target_negative_requested": true,
                  "path_negative_requested": false
                }
              }
            ]
          },
          "candidate_minus_baseline_utility": 0.0,
          "robustness_passed": true,
          "utility_improved": false,
          "promotion_gate_passed": false,
          "interpretation_limit": "Generalization is tested on generated graph compositions not assigned training profile labels; oracle and constraints remain internal graph semantics, not external factual truth."
        },
        "promotion_accepted": false,
        "promotion_status": "not_promoted",
        "active_policy_changed": false,
        "active_policy_after": {
          "target_conflict": [
            "counterevidence_scan",
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier"
          ],
          "path_conflict": [
            "transitive_graph_search",
            "counterevidence_scan",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "multi_scope_conflict": [
            "counterevidence_scan",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup"
          ],
          "direct_branching": [
            "transitive_graph_search",
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ],
          "transitive_branching": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "direct_only": [
            "direct_lookup",
            "independent_integrity_verifier",
            "counterevidence_scan",
            "transitive_graph_search"
          ],
          "transitive_deep": [
            "transitive_graph_search",
            "independent_integrity_verifier",
            "direct_lookup",
            "counterevidence_scan"
          ],
          "transitive_shallow": [
            "transitive_graph_search",
            "direct_lookup",
            "counterevidence_scan",
            "independent_integrity_verifier"
          ],
          "unsupported": [
            "direct_lookup",
            "transitive_graph_search",
            "independent_integrity_verifier",
            "counterevidence_scan"
          ]
        },
        "isolation_invariants": {
          "case_ids_pairwise_disjoint": true,
          "entity_namespaces_pairwise_disjoint": true,
          "holdout_not_used_for_candidate_selection": true,
          "holdout_not_used_for_training_policy": true,
          "holdout_does_not_change_training_support": true,
          "open_world_cases_have_no_profile_or_expected_order_labels": true,
          "open_world_only_gates_promotion_not_candidate_order": true,
          "open_world_oracle_match_rate_is_perfect": true,
          "open_world_structural_constraints_all_pass": true,
          "all_profiles_have_safe_complete_order": true,
          "holdout_reasoner_verdicts_match_oracle": true,
          "holdout_profile_extraction_correct": true
        },
        "isolation_passed": true,
        "training_case_ids": [
          "CXT0001",
          "CXT0002",
          "CXT0003",
          "CXT0004",
          "CXT0005",
          "CXT0006",
          "CXT0007",
          "CXT0008",
          "CXT0009",
          "CXT0010",
          "CXT0011",
          "CXT0012",
          "CXT0013",
          "CXT0014",
          "CXT0015",
          "CXT0016",
          "CXT0017",
          "CXT0018",
          "CXT0019",
          "CXT0020",
          "CXT0021",
          "CXT0022",
          "CXT0023",
          "CXT0024",
          "CXT0025",
          "CXT0026",
          "CXT0027",
          "CXT0028",
          "CXT0029",
          "CXT0030",
          "CXT0031",
          "CXT0032",
          "CXT0033",
          "CXT0034",
          "CXT0035",
          "CXT0036"
        ],
        "validation_case_ids": [
          "CXV0001",
          "CXV0002",
          "CXV0003",
          "CXV0004",
          "CXV0005",
          "CXV0006",
          "CXV0007",
          "CXV0008",
          "CXV0009",
          "CXV0010",
          "CXV0011",
          "CXV0012",
          "CXV0013",
          "CXV0014",
          "CXV0015",
          "CXV0016",
          "CXV0017",
          "CXV0018"
        ],
        "holdout_case_ids": [
          "CXH0001",
          "CXH0002",
          "CXH0003",
          "CXH0004",
          "CXH0005",
          "CXH0006",
          "CXH0007",
          "CXH0008",
          "CXH0009",
          "CXH0010",
          "CXH0011",
          "CXH0012",
          "CXH0013",
          "CXH0014",
          "CXH0015",
          "CXH0016",
          "CXH0017",
          "CXH0018"
        ],
        "training_profile_set": [
          "direct_branching",
          "direct_only",
          "multi_scope_conflict",
          "path_conflict",
          "target_conflict",
          "transitive_branching",
          "transitive_deep",
          "transitive_shallow",
          "unsupported"
        ],
        "validation_profile_set": [
          "direct_branching",
          "direct_only",
          "multi_scope_conflict",
          "path_conflict",
          "target_conflict",
          "transitive_branching",
          "transitive_deep",
          "transitive_shallow",
          "unsupported"
        ],
        "holdout_profile_set": [
          "direct_branching",
          "direct_only",
          "multi_scope_conflict",
          "path_conflict",
          "target_conflict",
          "transitive_branching",
          "transitive_deep",
          "transitive_shallow",
          "unsupported"
        ],
        "candidate_policy_source": "observed_reasoner_evidence_priority_scores",
        "open_world_promotion_gate_passed": false,
        "fixture_expected_orders_used_for_candidate_selection": false,
        "independent_evaluator": "observed_evidence_constraints_plus_position_discounted_relevance_and_unlabelled_open_world_compositions",
        "records_facts_changed": false,
        "records_training_ledger_changed": false,
        "records_user_outcomes_changed": false,
        "epistemic_limit": "Kebijakan diturunkan dari output reasoner; evaluasi tetap memakai graf sintetis dan oracle internal, bukan bukti kebenaran eksternal."
      }
    }
  },
  "invariants": {
    "user_facts_unchanged": true,
    "training_ledger_unchanged": true,
    "caller_outcomes_unchanged": true,
    "user_feedback_preferences_unchanged": true,
    "mutation_policy_unchanged": true,
    "reasoner_config_unchanged": true,
    "contextual_policy_unchanged": true,
    "coarse_composite_policy_unchanged": true,
    "only_synthetic_graph_cases_used": true,
    "actual_persisted_policy_not_changed_by_diagnostic": true,
    "synthetic_only_evaluation_does_not_import_persisted_facts_or_training_ledgers": true,
    "holdouts_not_used_to_select_candidates": true,
    "no_global_plateau_claim_from_flatline": true
  },
  "epistemic_limit": "A replay flatline describes only the tested policy, search algorithm, synthetic graph generator, and seeds. It does not prove global strategy-space saturation or external factual correctness.",
  "isolation_passed": true,
  "evaluation_id": "LPD00004",
  "recorded_at": "2026-10-24T16:08:50.517156+00:00",
  "events": [
    {
      "sequence": 1,
      "event_id": "b8b679ca65ea",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "perception",
      "event_type": "input_received",
      "payload": {
        "text": "/learning-plateau-diagnostic 36 18 18 24001",
        "channel": "structured_command"
      }
    },
    {
      "sequence": 2,
      "event_id": "e59ccc094073",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "language_area",
      "event_type": "command_parsed",
      "payload": {
        "command_kind": "learning_plateau_diagnostic"
      }
    },
    {
      "sequence": 3,
      "event_id": "8f7f6af45c7b",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
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
      "sequence": 4,
      "event_id": "87cf53a00e34",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "learning_plateau_lab",
      "event_type": "candidate_proposed",
      "payload": {
        "kind": "learning_plateau_diagnostic_report",
        "confidence": 0.95,
        "content": {
          "evaluation_id": "LPD00004",
          "diagnosis": "REPLAY_NO_GAIN_NEW_SEED_NO_PROMOTION",
          "fresh_promotion": true,
          "replay_no_gain": true,
          "independent_seed_promotion": false,
          "isolation_passed": true
        }
      }
    },
    {
      "sequence": 5,
      "event_id": "b405ce6cc4c4",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "global_workspace",
      "event_type": "workspace_broadcast",
      "payload": {
        "items": [
          {
            "source": "learning_plateau_lab",
            "kind": "learning_plateau_diagnostic_report",
            "score": 0.758
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
      "sequence": 6,
      "event_id": "88c471f0da85",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "learning_plateau_lab",
      "event_type": "learning_plateau_diagnostic_completed",
      "payload": {
        "evaluation_id": "LPD00004",
        "seed": 24001,
        "diagnosis": "REPLAY_NO_GAIN_NEW_SEED_NO_PROMOTION",
        "persistent_policy_mutated": false,
        "isolation_passed": true
      }
    },
    {
      "sequence": 7,
      "event_id": "984d3cd0960c",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "executive_controller",
      "event_type": "command_executed",
      "payload": {
        "action": "diagnose_learning_plateau_under_controlled_replays",
        "mode": "explicit_user_command"
      }
    },
    {
      "sequence": 8,
      "event_id": "8b66c0b448aa",
      "timestamp": "2026-10-24T16:08:50.731439+00:00",
      "cycle": 1,
      "source": "language_area",
      "event_type": "response_generated",
      "payload": {
        "action": "diagnose_learning_plateau_under_controlled_replays",
        "response": "Learning plateau LPD00004: diagnosis=REPLAY_NO_GAIN_NEW_SEED_NO_PROMOTION; fresh_promotion=True; replay_no_gain=True; new_seed_promotion=False; persistent_policy_changed=False."
      }
    },
    {
      "sequence": 9,
      "event_id": "486e7dca5fbc",
      "timestamp": "2026-10-24T16:08:50.832071+00:00",
      "cycle": 1,
      "source": "hippocampus",
      "event_type": "episode_stored",
      "payload": {
        "episode_id": "819bf410bc5e",
        "action": "diagnose_learning_plateau_under_controlled_replays",
        "interaction_type": "structured_command"
      }
    }
  ],
  "episode_id": "819bf410bc5e"
}
COGNITIVE_UPDATE> siklus=1; WORKSPACE> learning_plateau_lab:learning_plateau_diagnostic_report (0.76), prefrontal_cortex:active_goal (0.61)

KAMU> /learning-plateau-report
{
  "suite_version": "controlled-learning-plateau-diagnostic-v1",
  "evaluation_runs": 4,
  "latest_evaluation_id": "LPD00004",
  "latest_diagnosis": "REPLAY_NO_GAIN_NEW_SEED_NO_PROMOTION",
  "latest_status": "PASS",
  "latest_seed_plan": {
    "fresh_start_seed": 24001,
    "exact_replay_seed": 24001,
    "independent_seed": 1024004
  },
  "latest_replay_no_gain": true,
  "latest_independent_seed_promoted": false,
  "latest_current_policy_open_world_gain": 0.0,
  "active_policy_profile_count": 0,
  "latest_explanation": "Pengulangan identik stabil tanpa kenaikan; pencarian seed baru juga belum menemukan perbaikan yang memenuhi gate. Kesimpulan dibatasi pada ukuran, generator, dan seed uji ini.",
  "epistemic_limit": "Flatline pada replay bukan bukti plateau global; hanya berlaku pada ruang uji, generator dan seed yang digunakan."
}

KAMU> /status
{
  "workspace": {
    "cycle": 1,
    "goal": "memahami input dan merespons dengan jujur",
    "arousal": 0.35,
    "learning_rate": 0.2,
    "prediction_error": 0.0,
    "last_action": "diagnose_learning_plateau_under_controlled_replays",
    "working_memory_size": 2,
    "broadcast": [
      {
        "source": "learning_plateau_lab",
        "kind": "learning_plateau_diagnostic_report",
        "content": {
          "evaluation_id": "LPD00004",
          "diagnosis": "REPLAY_NO_GAIN_NEW_SEED_NO_PROMOTION",
          "fresh_promotion": true,
          "replay_no_gain": true,
          "independent_seed_promotion": false,
          "isolation_passed": true
        },
        "confidence": 0.95,
        "novelty": 0.94,
        "urgency": 0.0,
        "goal_relevance": 0.95,
        "evidence": [
          "perubahan atau rencana berasal dari perintah eksplisit pengguna"
        ],
        "score": 0.758
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
  "cognitive_cycles_total": 5,
  "episodic_memories": 5,
  "semantic_relations": 0,
  "hypotheses": 0,
  "hypothesis_evidence_records": 0,
  "provenance_claims": 0,
  "provenance_evidence_records": 0,
  "provenance_external_checks": 0,
  "memory_schema_version": 21,
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
  "counterexample_evaluation_runs": 0,
  "adversarial_boundary_evaluation_runs": 0,
  "failure_guided_evaluation_runs": 0,
  "compositional_evaluation_runs": 0,
  "adaptive_interaction_evaluation_runs": 0,
  "strategy_synthesis_evaluation_runs": 0,
  "latest_strategy_synthesis_promotion_status": null,
  "composite_strategy_evaluation_runs": 0,
  "active_composite_strategy_contexts": [],
  "latest_composite_strategy_promotion_status": null,
  "contextual_composition_evaluation_runs": 0,
  "learning_plateau_diagnostic_runs": 4,
  "latest_learning_plateau_diagnosis": "REPLAY_NO_GAIN_NEW_SEED_NO_PROMOTION",
  "active_contextual_composition_profiles": [],
  "latest_contextual_composition_promotion_status": null,
  "reasoner_search_config": {
    "max_depth": 6,
    "max_paths": 3
  },
  "latest_adaptive_interaction_all_matched": null,
  "latest_adaptive_interaction_oracle_match_rate": null,
  "latest_compositional_all_matched": null,
  "latest_compositional_oracle_match_rate": null,
  "latest_boundary_suite_pass_rate": null,
  "latest_counterexample_oracle_match_rate": null,
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
    "systematic_adversarial_graph_boundary_and_metamorphic_suite",
    "failure_guided_case_discovery_with_sealed_holdout",
    "compositional_graph_interaction_lab",
    "adaptive_higher_order_interaction_discovery_lab",
    "counterexample_guided_strategy_synthesis_with_validation_and_sealed_holdout",
    "compositional_strategy_learning_with_validation_and_sealed_holdout",
    "context_conditioned_composition_learning_with_holdout",
    "independent_verifier",
    "multi_strategy_reasoner",
    "global_workspace"
  ],
  "llm_used": false
}

KAMU> /quit
Memori disimpan. Sampai jumpa.


putra@L MINGW64 ~/Downloads/Video/BRAIN
$ python -m compileall -q brain_ai tests scripts
python -m unittest discover -s tests -v
python scripts/verify_release.py
test_default_three_motif_suite_matches_oracle_and_keeps_holdout_separate (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_default_three_motif_suite_matches_oracle_and_keeps_holdout_separate) ... ok
test_each_case_composes_three_motifs_with_target_endpoints_shared (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_each_case_composes_three_motifs_with_target_endpoints_shared) ... ok
test_holdout_only_failure_history_does_not_change_training_priority (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_holdout_only_failure_history_does_not_change_training_priority) ... ok
test_invalid_counts_and_seed_are_rejected (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_invalid_counts_and_seed_are_rejected) ... ok
test_report_states_oracle_scope_not_external_truth (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_report_states_oracle_scope_not_external_truth) ... ok
test_same_seed_produces_identical_cases_and_priorities (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_same_seed_produces_identical_cases_and_priorities) ... ok
test_training_and_holdout_have_disjoint_motif_families_and_recipe_ids (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_training_and_holdout_have_disjoint_motif_families_and_recipe_ids) ... ok
test_training_diagnosis_prioritizes_related_recipe (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_training_diagnosis_prioritizes_related_recipe) ... ok
test_training_failure_history_can_affect_training_recipe_but_never_holdout_recipe (test_adaptive_interaction_lab_v018.AdaptiveInteractionCoreTests.test_training_failure_history_can_affect_training_recipe_but_never_holdout_recipe) ... ok
test_cli_search_report_and_status (test_adaptive_interaction_lab_v018.AdaptiveInteractionPersistenceTests.test_cli_search_report_and_status) ... ok
test_experiment_does_not_mutate_facts_learning_or_policy (test_adaptive_interaction_lab_v018.AdaptiveInteractionPersistenceTests.test_experiment_does_not_mutate_facts_learning_or_policy) ... ok
test_report_persists_and_ids_increase_after_restart (test_adaptive_interaction_lab_v018.AdaptiveInteractionPersistenceTests.test_report_persists_and_ids_increase_after_restart) ... ok
test_schemas_8_through_17_migrate_to_18_without_data_loss (test_adaptive_interaction_lab_v018.AdaptiveInteractionPersistenceTests.test_schemas_8_through_17_migrate_to_18_without_data_loss) ... ok
test_every_fixture_has_all_six_semantics_preserving_variants (test_adversarial_suite_v015.AdversarialBoundarySuiteCoreTests.test_every_fixture_has_all_six_semantics_preserving_variants) ... ok
test_invalid_seed_is_rejected (test_adversarial_suite_v015.AdversarialBoundarySuiteCoreTests.test_invalid_seed_is_rejected) ... ok
test_report_distinguishes_oracle_match_from_external_truth (test_adversarial_suite_v015.AdversarialBoundarySuiteCoreTests.test_report_distinguishes_oracle_match_from_external_truth) ... ok
test_report_is_deterministic_for_same_seed (test_adversarial_suite_v015.AdversarialBoundarySuiteCoreTests.test_report_is_deterministic_for_same_seed) ... ok
test_suite_contains_cycle_self_loop_conflict_and_alternative_path_edges (test_adversarial_suite_v015.AdversarialBoundarySuiteCoreTests.test_suite_contains_cycle_self_loop_conflict_and_alternative_path_edges) ... ok
test_systematic_suite_covers_24_fixtures_and_144_variants (test_adversarial_suite_v015.AdversarialBoundarySuiteCoreTests.test_systematic_suite_covers_24_fixtures_and_144_variants) ... ok
test_boundary_report_persists_across_restart_and_is_compact (test_adversarial_suite_v015.AdversarialBoundarySuitePersistenceTests.test_boundary_report_persists_across_restart_and_is_compact) ... ok
test_brain_suite_does_not_mutate_semantic_or_learning_state (test_adversarial_suite_v015.AdversarialBoundarySuitePersistenceTests.test_brain_suite_does_not_mutate_semantic_or_learning_state) ... ok
test_cli_boundary_suite_and_report (test_adversarial_suite_v015.AdversarialBoundarySuitePersistenceTests.test_cli_boundary_suite_and_report) ... ok
test_schema13_migrates_to18_without_losing_existing_training_state (test_adversarial_suite_v015.AdversarialBoundarySuitePersistenceTests.test_schema13_migrates_to18_without_losing_existing_training_state) ... ok
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
test_case_ids_and_entity_namespaces_are_disjoint_across_splits (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_case_ids_and_entity_namespaces_are_disjoint_across_splits) ... ok
test_cli_composite_learning_end_to_end_and_schema (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_cli_composite_learning_end_to_end_and_schema) ... ok
test_conflict_priority_invariant_is_preserved (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_conflict_priority_invariant_is_preserved) ... ok
test_context_compositions_match_internal_task_contracts (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_context_compositions_match_internal_task_contracts) ... ok
test_default_training_learns_composition_and_beats_baseline (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_default_training_learns_composition_and_beats_baseline) ... ok
test_experiment_does_not_touch_caller_learning_state (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_experiment_does_not_touch_caller_learning_state) ... ok
test_holdout_is_not_used_for_candidate_selection_or_priority (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_holdout_is_not_used_for_candidate_selection_or_priority) ... ok
test_invalid_counts_and_seed_are_rejected (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_invalid_counts_and_seed_are_rejected) ... ok
test_learned_policy_contains_all_contexts_and_every_component_once (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_learned_policy_contains_all_contexts_and_every_component_once) ... ok
test_learning_output_is_deterministic_for_fixed_seed (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_learning_output_is_deterministic_for_fixed_seed) ... ok
test_malformed_persisted_policy_is_repaired_to_empty (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_malformed_persisted_policy_is_repaired_to_empty) ... ok
test_oracle_and_fixture_verdicts_match_for_every_split (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_oracle_and_fixture_verdicts_match_for_every_split) ... ok
test_order_validator_rejects_duplicates_and_unknown_components (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_order_validator_rejects_duplicates_and_unknown_components) ... ok
test_policy_and_report_persist_after_restart (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_policy_and_report_persist_after_restart) ... ok
test_policy_normalizer_discards_invalid_contexts_and_orders (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_policy_normalizer_discards_invalid_contexts_and_orders) ... ok
test_promoted_policy_orders_actual_reasoning_but_never_overrides_conflicts (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_promoted_policy_orders_actual_reasoning_but_never_overrides_conflicts) ... ok
test_schema18_state_migrates_and_keeps_facts_and_training (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_schema18_state_migrates_and_keeps_facts_and_training) ... ok
test_second_run_does_not_repromote_unchanged_policy (test_composite_strategy_lab_v020.CompositeStrategyLabV020Tests.test_second_run_does_not_repromote_unchanged_policy) ... ok
test_compositions_are_multi_motif_and_holdout_recipes_are_disjoint (test_composition_lab_v017.CompositionalLabCoreTests.test_compositions_are_multi_motif_and_holdout_recipes_are_disjoint) ... ok
test_default_composition_suite_matches_internal_oracle_on_train_and_holdout (test_composition_lab_v017.CompositionalLabCoreTests.test_default_composition_suite_matches_internal_oracle_on_train_and_holdout) ... ok
test_holdout_only_history_never_changes_training_priority (test_composition_lab_v017.CompositionalLabCoreTests.test_holdout_only_history_never_changes_training_priority) ... ok
test_invalid_case_counts_and_seed_are_rejected (test_composition_lab_v017.CompositionalLabCoreTests.test_invalid_case_counts_and_seed_are_rejected) ... ok
test_isolation_flags_and_epistemic_scope_are_explicit (test_composition_lab_v017.CompositionalLabCoreTests.test_isolation_flags_and_epistemic_scope_are_explicit) ... ok
test_only_training_mismatch_changes_composition_priority (test_composition_lab_v017.CompositionalLabCoreTests.test_only_training_mismatch_changes_composition_priority) ... ok
test_same_seed_is_deterministic_for_cases_priority_and_outcomes (test_composition_lab_v017.CompositionalLabCoreTests.test_same_seed_is_deterministic_for_cases_priority_and_outcomes) ... ok
test_training_diagnosis_prioritizes_related_composition (test_composition_lab_v017.CompositionalLabCoreTests.test_training_diagnosis_prioritizes_related_composition) ... ok
test_cli_search_report_and_status (test_composition_lab_v017.CompositionalLabPersistenceTests.test_cli_search_report_and_status) ... ok
test_report_persists_across_restart_and_ids_are_monotonic (test_composition_lab_v017.CompositionalLabPersistenceTests.test_report_persists_across_restart_and_ids_are_monotonic) ... ok
test_run_does_not_mutate_user_facts_learning_or_policy (test_composition_lab_v017.CompositionalLabPersistenceTests.test_run_does_not_mutate_user_facts_learning_or_policy) ... ok
test_schema_8_through_17_migrate_without_losing_core_learning_state (test_composition_lab_v017.CompositionalLabPersistenceTests.test_schema_8_through_17_migrate_without_losing_core_learning_state) ... ok
test_candidate_policy_has_all_profiles_and_preserves_every_component (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_candidate_policy_has_all_profiles_and_preserves_every_component) ... ok
test_cli_learning_and_report_smoke (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_cli_learning_and_report_smoke) ... ok
test_conflict_policy_keeps_counterevidence_priority_after_promotion (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_conflict_policy_keeps_counterevidence_priority_after_promotion) ... ok
test_contextual_policy_is_persisted_and_used_by_interactive_reasoner (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_contextual_policy_is_persisted_and_used_by_interactive_reasoner) ... ok
test_default_contextual_learning_promotes_after_validation_and_holdout (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_default_contextual_learning_promotes_after_validation_and_holdout) ... ok
test_duplicate_assertions_do_not_create_false_branching (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_duplicate_assertions_do_not_create_false_branching) ... ok
test_each_structural_fixture_is_classified_by_observed_features (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_each_structural_fixture_is_classified_by_observed_features) ... ok
test_invalid_counts_and_seed_fail_closed (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_invalid_counts_and_seed_fail_closed) ... ok
test_lab_does_not_mutate_world_facts_learning_or_existing_policies (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_lab_does_not_mutate_world_facts_learning_or_existing_policies) ... ok
test_large_composition_run_preserves_holdout_isolation (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_large_composition_run_preserves_holdout_isolation) ... ok
test_policy_validation_rejects_incomplete_and_duplicate_orders (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_policy_validation_rejects_incomplete_and_duplicate_orders) ... ok
test_schema19_migration_preserves_existing_data_and_adds_contextual_defaults (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_schema19_migration_preserves_existing_data_and_adds_contextual_defaults) ... ok
test_seed_is_deterministic_and_split_namespaces_are_distinct (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_seed_is_deterministic_and_split_namespaces_are_distinct) ... ok
test_split_ids_and_entities_are_disjoint (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_split_ids_and_entities_are_disjoint) ... ok
test_structural_conflicts_are_classified_before_direct_edges (test_contextual_composition_v021.ContextualCompositionLabV021Tests.test_structural_conflicts_are_classified_before_direct_edges) ... ok
test_cli_rejects_invalid_search_args_without_crashing (test_counterexample_lab_v014.CounterexampleCLITests.test_cli_rejects_invalid_search_args_without_crashing) ... ok
test_cli_runs_search_and_report (test_counterexample_lab_v014.CounterexampleCLITests.test_cli_runs_search_and_report) ... ok
test_minimizer_deletes_irrelevant_facts_while_preserving_mocked_mismatch (test_counterexample_lab_v014.CounterexampleOracleTests.test_minimizer_deletes_irrelevant_facts_while_preserving_mocked_mismatch) ... ok
test_minimizer_rejects_non_counterexample_as_non_applicable (test_counterexample_lab_v014.CounterexampleOracleTests.test_minimizer_rejects_non_counterexample_as_non_applicable) ... ok
test_oracle_detects_negative_intermediate_edge (test_counterexample_lab_v014.CounterexampleOracleTests.test_oracle_detects_negative_intermediate_edge) ... ok
test_oracle_direct_assertion_is_unverified_not_true (test_counterexample_lab_v014.CounterexampleOracleTests.test_oracle_direct_assertion_is_unverified_not_true) ... ok
test_oracle_does_not_infer_from_disconnected_graph (test_counterexample_lab_v014.CounterexampleOracleTests.test_oracle_does_not_infer_from_disconnected_graph) ... ok
test_oracle_keeps_explicit_target_negative_as_conflict (test_counterexample_lab_v014.CounterexampleOracleTests.test_oracle_keeps_explicit_target_negative_as_conflict) ... ok
test_oracle_transitive_path_is_unverified (test_counterexample_lab_v014.CounterexampleOracleTests.test_oracle_transitive_path_is_unverified) ... ok
test_production_reasoner_matches_oracle_on_default_suite (test_counterexample_lab_v014.CounterexampleOracleTests.test_production_reasoner_matches_oracle_on_default_suite) ... ok
test_search_covers_all_boundary_categories (test_counterexample_lab_v014.CounterexampleOracleTests.test_search_covers_all_boundary_categories) ... ok
test_search_is_deterministic_for_same_seed (test_counterexample_lab_v014.CounterexampleOracleTests.test_search_is_deterministic_for_same_seed) ... ok
test_search_rejects_invalid_case_counts_and_seeds (test_counterexample_lab_v014.CounterexampleOracleTests.test_search_rejects_invalid_case_counts_and_seeds) ... ok
test_stress_search_matches_oracle_on_250_cases_with_an_independent_seed (test_counterexample_lab_v014.CounterexampleOracleTests.test_stress_search_matches_oracle_on_250_cases_with_an_independent_seed) ... ok
test_empty_counterexample_report (test_counterexample_lab_v014.CounterexamplePersistenceTests.test_empty_counterexample_report) ... ok
test_evaluation_does_not_mutate_facts_training_outcomes_or_policy (test_counterexample_lab_v014.CounterexamplePersistenceTests.test_evaluation_does_not_mutate_facts_training_outcomes_or_policy) ... ok
test_evaluation_ids_remain_monotonic_after_history_cap (test_counterexample_lab_v014.CounterexamplePersistenceTests.test_evaluation_ids_remain_monotonic_after_history_cap) ... ok
test_report_persists_after_restart (test_counterexample_lab_v014.CounterexamplePersistenceTests.test_report_persists_after_restart) ... ok
test_schema12_migrates_to_schema15_without_losing_existing_data (test_counterexample_lab_v014.CounterexamplePersistenceTests.test_schema12_migrates_to_schema15_without_losing_existing_data) ... ok
test_schema_8_through_12_migrate_to_schema15_without_losing_core_data (test_counterexample_lab_v014.CounterexamplePersistenceTests.test_schema_8_through_12_migrate_to_schema15_without_losing_core_data) ... ok
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
test_cli_runs_training_and_holdout_search_and_report (test_failure_guided_lab_v016.FailureGuidedCliTests.test_cli_runs_training_and_holdout_search_and_report) ... ok
test_declared_training_failures_prioritize_related_case_families (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_declared_training_failures_prioritize_related_case_families) ... ok
test_default_suite_matches_oracle_in_training_and_sealed_holdout (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_default_suite_matches_oracle_in_training_and_sealed_holdout) ... ok
test_holdout_only_history_never_influences_training_priority (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_holdout_only_history_never_influences_training_priority) ... ok
test_invalid_counts_and_seed_are_rejected (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_invalid_counts_and_seed_are_rejected) ... ok
test_mismatch_queue_is_empty_when_all_cases_match (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_mismatch_queue_is_empty_when_all_cases_match) ... ok
test_only_previous_training_mismatch_can_change_priorities (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_only_previous_training_mismatch_can_change_priorities) ... ok
test_prior_boundary_failures_prioritize_related_family (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_prior_boundary_failures_prioritize_related_family) ... ok
test_same_seed_produces_same_cases_and_priority (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_same_seed_produces_same_cases_and_priority) ... ok
test_training_and_holdout_rows_are_labeled_for_audit (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_training_and_holdout_rows_are_labeled_for_audit) ... ok
test_training_and_holdout_use_disjoint_ids_and_template_families (test_failure_guided_lab_v016.FailureGuidedGenerationTests.test_training_and_holdout_use_disjoint_ids_and_template_families) ... ok
test_empty_snapshot_has_no_latest_report (test_failure_guided_lab_v016.FailureGuidedPersistenceTests.test_empty_snapshot_has_no_latest_report) ... ok
test_report_persists_across_restart_and_ids_increase (test_failure_guided_lab_v016.FailureGuidedPersistenceTests.test_report_persists_across_restart_and_ids_increase) ... ok
test_run_does_not_mutate_facts_training_outcomes_preferences_or_policy (test_failure_guided_lab_v016.FailureGuidedPersistenceTests.test_run_does_not_mutate_facts_training_outcomes_preferences_or_policy) ... ok
test_schema_8_through_17_migrate_without_losing_existing_data (test_failure_guided_lab_v016.FailureGuidedPersistenceTests.test_schema_8_through_17_migrate_without_losing_existing_data) ... ok
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
test_schema_v8_state_migrates_to_schema11_without_losing_fields (test_failure_learning_v0101.FailureLearningCoreTests.test_schema_v8_state_migrates_to_schema11_without_losing_fields) ... ok
test_unexpected_conflict_maps_to_integrity_review_not_auto_resolution (test_failure_learning_v0101.FailureLearningCoreTests.test_unexpected_conflict_maps_to_integrity_review_not_auto_resolution) ... ok
test_cli_evaluate_and_report (test_generalization_lab_v012.GeneralizationLabCLITests.test_cli_evaluate_and_report) ... ok
test_cli_smoke_with_cp1252 (test_generalization_lab_v012.GeneralizationLabCLITests.test_cli_smoke_with_cp1252) ... ok
test_alpha_renaming_preserves_all_strategy_statuses (test_generalization_lab_v012.GeneralizationLabCoreTests.test_alpha_renaming_preserves_all_strategy_statuses) ... ok
test_conflicts_are_never_downgraded_by_transformations (test_generalization_lab_v012.GeneralizationLabCoreTests.test_conflicts_are_never_downgraded_by_transformations) ... ok
test_disconnected_cycle_does_not_change_target_query (test_generalization_lab_v012.GeneralizationLabCoreTests.test_disconnected_cycle_does_not_change_target_query) ... ok
test_duplicate_assertions_do_not_change_structural_result (test_generalization_lab_v012.GeneralizationLabCoreTests.test_duplicate_assertions_do_not_change_structural_result) ... ok
test_evaluation_is_deterministic (test_generalization_lab_v012.GeneralizationLabCoreTests.test_evaluation_is_deterministic) ... ok
test_evaluation_uses_separate_isolated_memory_by_construction (test_generalization_lab_v012.GeneralizationLabCoreTests.test_evaluation_uses_separate_isolated_memory_by_construction) ... ok
test_fact_order_permutation_preserves_results (test_generalization_lab_v012.GeneralizationLabCoreTests.test_fact_order_permutation_preserves_results) ... ok
test_invalid_context_policy_rejected (test_generalization_lab_v012.GeneralizationLabCoreTests.test_invalid_context_policy_rejected) ... ok
test_irrelevant_distractors_and_conflict_do_not_leak_to_query (test_generalization_lab_v012.GeneralizationLabCoreTests.test_irrelevant_distractors_and_conflict_do_not_leak_to_query) ... ok
test_scope_does_not_claim_external_truth (test_generalization_lab_v012.GeneralizationLabCoreTests.test_scope_does_not_claim_external_truth) ... ok
test_suite_covers_every_seed_under_every_transformation (test_generalization_lab_v012.GeneralizationLabCoreTests.test_suite_covers_every_seed_under_every_transformation) ... ok
test_evaluation_does_not_change_user_facts_trials_or_active_policy (test_generalization_lab_v012.GeneralizationLabPersistenceTests.test_evaluation_does_not_change_user_facts_trials_or_active_policy) ... ok
test_evaluation_report_persists_across_restart (test_generalization_lab_v012.GeneralizationLabPersistenceTests.test_evaluation_report_persists_across_restart) ... ok
test_repeated_evaluation_persists_bounded_history_and_does_not_train (test_generalization_lab_v012.GeneralizationLabPersistenceTests.test_repeated_evaluation_persists_bounded_history_and_does_not_train) ... ok
test_schema10_state_migrates_to_schema11_and_keeps_known_fields (test_generalization_lab_v012.GeneralizationLabPersistenceTests.test_schema10_state_migrates_to_schema11_and_keeps_known_fields) ... ok
test_cli_banner_matches_release_version (test_learning_cycle.LearningCycleCLITests.test_cli_banner_matches_release_version) ... ok
test_feedback_does_not_remove_conflict_from_reasoning (test_learning_cycle.LearningCycleCLITests.test_feedback_does_not_remove_conflict_from_reasoning) ... ok
test_outcome_benchmark_trains_applicability_and_holdout_stays_out_of_ledger (test_learning_cycle.LearningCycleCLITests.test_outcome_benchmark_trains_applicability_and_holdout_stays_out_of_ledger) ... ok
test_positive_feedback_updates_strategy_value_through_cli (test_learning_cycle.LearningCycleCLITests.test_positive_feedback_updates_strategy_value_through_cli) ... ok
test_reasoning_cli_survives_legacy_cp1252_output (test_learning_cycle.LearningCycleCLITests.test_reasoning_cli_survives_legacy_cp1252_output) ... ok
test_strategy_learning_persists_across_cli_restart (test_learning_cycle.LearningCycleCLITests.test_strategy_learning_persists_across_cli_restart) ... ok
test_strategy_outcome_can_be_recorded_against_persisted_reasoning_episode (test_learning_cycle.LearningCycleCLITests.test_strategy_outcome_can_be_recorded_against_persisted_reasoning_episode) ... ok
test_diagnostic_does_not_mutate_user_memory_or_active_policy (test_learning_plateau_v024.LearningPlateauV024Tests.test_diagnostic_does_not_mutate_user_memory_or_active_policy) ... ok
test_fresh_replay_and_new_seed_are_distinguished (test_learning_plateau_v024.LearningPlateauV024Tests.test_fresh_replay_and_new_seed_are_distinguished) ... ok
test_invalid_counts_or_seed_fail_closed (test_learning_plateau_v024.LearningPlateauV024Tests.test_invalid_counts_or_seed_fail_closed) ... ok
test_schema20_migration_preserves_existing_user_and_learning_state (test_learning_plateau_v024.LearningPlateauV024Tests.test_schema20_migration_preserves_existing_user_and_learning_state) ... ok
test_cli_mutation_command_and_report_smoke (test_mutation_lab_v011.MutationLabTests.test_cli_mutation_command_and_report_smoke) ... ok
test_conflict_strategy_cannot_be_mutated_away_from_counterevidence (test_mutation_lab_v011.MutationLabTests.test_conflict_strategy_cannot_be_mutated_away_from_counterevidence) ... ok
test_evaluator_never_touches_users_semantic_memory (test_mutation_lab_v011.MutationLabTests.test_evaluator_never_touches_users_semantic_memory) ... ok
test_holdout_validated_mutation_can_repair_bad_legacy_override (test_mutation_lab_v011.MutationLabTests.test_holdout_validated_mutation_can_repair_bad_legacy_override) ... ok
test_invalid_context_strategy_or_empty_rationale_rejected (test_mutation_lab_v011.MutationLabTests.test_invalid_context_strategy_or_empty_rationale_rejected) ... ok
test_no_improvement_mutation_is_rejected_and_does_not_activate (test_mutation_lab_v011.MutationLabTests.test_no_improvement_mutation_is_rejected_and_does_not_activate) ... ok
test_promoted_policy_changes_primary_focus_but_not_conclusion_or_conflict_safety (test_mutation_lab_v011.MutationLabTests.test_promoted_policy_changes_primary_focus_but_not_conclusion_or_conflict_safety) ... ok
test_reference_evaluator_uses_separate_holdout_and_is_correct_on_all_probes (test_mutation_lab_v011.MutationLabTests.test_reference_evaluator_uses_separate_holdout_and_is_correct_on_all_probes) ... ok
test_root_cause_analysis_adds_specific_debug_signal_to_failure_record (test_mutation_lab_v011.MutationLabTests.test_root_cause_analysis_adds_specific_debug_signal_to_failure_record) ... ok
test_schema_11_migrates_schema_10_and_persists_mutations (test_mutation_lab_v011.MutationLabTests.test_schema_11_migrates_schema_10_and_persists_mutations) ... ok
test_candidate_generalizes_to_open_world_compositions (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_candidate_generalizes_to_open_world_compositions) ... ok
test_composition_promotion_requires_open_world_gate (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_composition_promotion_requires_open_world_gate) ... ok
test_conflict_on_path_after_max_paths_display_cap_is_still_found (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_conflict_on_path_after_max_paths_display_cap_is_still_found) ... ok
test_generator_is_deterministic_and_has_no_expected_order_or_profile_labels (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_generator_is_deterministic_and_has_no_expected_order_or_profile_labels) ... ok
test_insufficient_profile_training_still_fails_closed (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_insufficient_profile_training_still_fails_closed) ... ok
test_open_world_baseline_is_not_misreported_as_structurally_safe (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_open_world_baseline_is_not_misreported_as_structurally_safe) ... ok
test_open_world_evaluation_does_not_mutate_cases_or_policy (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_open_world_evaluation_does_not_mutate_cases_or_policy) ... ok
test_policy_remains_safe_and_utility_improves_across_unseen_seed_namespaces (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_policy_remains_safe_and_utility_improves_across_unseen_seed_namespaces) ... ok
test_utility_flatline_on_open_world_blocks_promotion_without_rewriting_policy (test_open_world_v023.OpenWorldGeneralizationV023Tests.test_utility_flatline_on_open_world_blocks_promotion_without_rewriting_policy) ... ok
test_cli_version_flag_matches_package_version (test_release_identity_v0131.ReleaseIdentityTests.test_cli_version_flag_matches_package_version) ... ok
test_version_sources_are_consistent (test_release_identity_v0131.ReleaseIdentityTests.test_version_sources_are_consistent) ... ok
test_cli_train_and_routing_report (test_routing_evaluation_v013.RoutingEvaluationCLITests.test_cli_train_and_routing_report) ... ok
test_all_mode_separates_crossfit_train_and_pretrained_holdout (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_all_mode_separates_crossfit_train_and_pretrained_holdout) ... ok
test_crossfit_is_not_contaminated_by_a_target_case_already_in_main_ledger (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_crossfit_is_not_contaminated_by_a_target_case_already_in_main_ledger) ... ok
test_crossfit_uses_only_the_current_curated_train_cases_not_user_outcomes (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_crossfit_uses_only_the_current_curated_train_cases_not_user_outcomes) ... ok
test_every_context_has_a_routing_metric (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_every_context_has_a_routing_metric) ... ok
test_holdout_evaluation_is_auditable_and_labels_are_scoped (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_holdout_evaluation_is_auditable_and_labels_are_scoped) ... ok
test_holdout_ignores_active_mutations_and_caller_outcomes (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_holdout_ignores_active_mutations_and_caller_outcomes) ... ok
test_holdout_uses_pretrained_policy_and_does_not_change_training_ledger (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_holdout_uses_pretrained_policy_and_does_not_change_training_ledger) ... ok
test_invalid_benchmark_mode_does_not_record_routing_evaluation (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_invalid_benchmark_mode_does_not_record_routing_evaluation) ... ok
test_repeated_training_does_not_inflate_trials_but_records_new_evaluation (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_repeated_training_does_not_inflate_trials_but_records_new_evaluation) ... ok
test_route_report_handles_empty_history (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_route_report_handles_empty_history) ... ok
test_routing_evaluation_report_persists_after_restart (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_routing_evaluation_report_persists_after_restart) ... ok
test_schema11_migrates_to_schema12_without_losing_learning_data (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_schema11_migrates_to_schema12_without_losing_learning_data) ... ok
test_train_crossfit_never_changes_user_facts_or_active_policy (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_train_crossfit_never_changes_user_facts_or_active_policy) ... ok
test_train_routing_score_uses_leave_one_case_out_crossfit (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_train_routing_score_uses_leave_one_case_out_crossfit) ... ok
test_training_prediction_does_not_copy_holdout_ids_into_fold (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_training_prediction_does_not_copy_holdout_ids_into_fold) ... ok
test_untrained_holdout_uses_documented_safe_defaults (test_routing_evaluation_v013.RoutingEvaluationCoreTests.test_untrained_holdout_uses_documented_safe_defaults) ... ok
test_benchmark_fixtures_match_predeclared_strategy_and_conclusion_statuses (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_benchmark_fixtures_match_predeclared_strategy_and_conclusion_statuses) ... ok
test_benchmark_rejects_invalid_mode (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_benchmark_rejects_invalid_mode) ... ok
test_conflict_safety_override_cannot_be_downgraded_by_learned_routing (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_conflict_safety_override_cannot_be_downgraded_by_learned_routing) ... ok
test_declared_task_failure_reduces_applicability_and_persists_with_provenance (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_declared_task_failure_reduces_applicability_and_persists_with_provenance) ... ok
test_failed_diagnostic_outcomes_reduce_applicability_score (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_failed_diagnostic_outcomes_reduce_applicability_score) ... ok
test_holdout_does_not_train_or_change_the_learning_ledger (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_holdout_does_not_train_or_change_the_learning_ledger) ... ok
test_preference_feedback_and_benchmark_outcomes_are_separate_signals (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_preference_feedback_and_benchmark_outcomes_are_separate_signals) ... ok
test_repeated_training_runs_do_not_inflate_trial_counts (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_repeated_training_runs_do_not_inflate_trial_counts) ... ok
test_routing_is_learned_per_context_after_minimum_evaluator_cases (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_routing_is_learned_per_context_after_minimum_evaluator_cases) ... ok
test_schema11_persists_outcomes_and_loads_v7_state (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_schema11_persists_outcomes_and_loads_v7_state) ... ok
test_task_outcome_requires_reasoning_episode_evaluator_and_basis (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_task_outcome_requires_reasoning_episode_evaluator_and_basis) ... ok
test_training_cases_never_pollute_user_semantic_memory (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_training_cases_never_pollute_user_semantic_memory) ... ok
test_unseen_relation_uses_learned_focus_but_preserves_conclusion (test_strategy_learning_v010.StrategyApplicabilityLearningTests.test_unseen_relation_uses_learned_focus_but_preserves_conclusion) ... ok
test_cli_version_search_report_and_schema (test_strategy_synthesis_v019.StrategySynthesisCliTests.test_cli_version_search_report_and_schema) ... ok
test_invalid_search_args_do_not_crash_cli (test_strategy_synthesis_v019.StrategySynthesisCliTests.test_invalid_search_args_do_not_crash_cli) ... ok
test_already_broad_active_config_does_not_get_promoted_without_validation_gain (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_already_broad_active_config_does_not_get_promoted_without_validation_gain) ... ok
test_balanced_strategy_improves_validation_and_sealed_holdout (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_balanced_strategy_improves_validation_and_sealed_holdout) ... ok
test_candidate_configs_are_bounded_and_deduplicated (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_candidate_configs_are_bounded_and_deduplicated) ... ok
test_candidate_generation_does_not_use_validation_or_holdout_labels (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_candidate_generation_does_not_use_validation_or_holdout_labels) ... ok
test_case_generator_has_disjoint_namespaces_by_split (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_case_generator_has_disjoint_namespaces_by_split) ... ok
test_conflict_safety_rejects_missed_conflict_even_when_accuracy_is_high (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_conflict_safety_rejects_missed_conflict_even_when_accuracy_is_high) ... ok
test_false_positive_conflicts_may_not_increase (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_false_positive_conflicts_may_not_increase) ... ok
test_invalid_counts_seeds_and_configs_are_rejected (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_invalid_counts_seeds_and_configs_are_rejected) ... ok
test_safe_candidate_must_not_miss_conflicts_and_not_add_false_positives (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_safe_candidate_must_not_miss_conflicts_and_not_add_false_positives) ... ok
test_same_seed_is_deterministic_except_timestamp (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_same_seed_is_deterministic_except_timestamp) ... ok
test_split_ids_and_entity_namespaces_are_disjoint (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_split_ids_and_entity_namespaces_are_disjoint) ... ok
test_training_counterexamples_create_candidates_from_failure_topologies (test_strategy_synthesis_v019.StrategySynthesisCoreTests.test_training_counterexamples_create_candidates_from_failure_topologies) ... ok
test_config_and_report_persist_after_restart (test_strategy_synthesis_v019.StrategySynthesisPersistenceTests.test_config_and_report_persist_after_restart) ... ok
test_invalid_persisted_reasoner_config_falls_back_safely (test_strategy_synthesis_v019.StrategySynthesisPersistenceTests.test_invalid_persisted_reasoner_config_falls_back_safely) ... ok
test_promoted_reasoner_config_is_applied_without_mutating_facts_or_learning_ledgers (test_strategy_synthesis_v019.StrategySynthesisPersistenceTests.test_promoted_reasoner_config_is_applied_without_mutating_facts_or_learning_ledgers) ... ok
test_schema_17_migrates_without_losing_core_data (test_strategy_synthesis_v019.StrategySynthesisPersistenceTests.test_schema_17_migrates_without_losing_core_data) ... ok
test_status_exposes_config_and_synthesis_history (test_strategy_synthesis_v019.StrategySynthesisPersistenceTests.test_status_exposes_config_and_synthesis_history) ... ok
test_candidate_policy_has_complete_orders_for_all_nine_profiles (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_candidate_policy_has_complete_orders_for_all_nine_profiles) ... ok
test_independent_constraints_audit_accepts_observed_safe_orders (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_independent_constraints_audit_accepts_observed_safe_orders) ... ok
test_independent_constraints_reject_unsafe_conflict_order (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_independent_constraints_reject_unsafe_conflict_order) ... ok
test_new_graph_profiles_are_discovered_from_reasoner_output (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_new_graph_profiles_are_discovered_from_reasoner_output) ... ok
test_promotion_requires_independent_structural_audit_and_utility_gain (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_promotion_requires_independent_structural_audit_and_utility_gain) ... ok
test_structural_priority_scores_are_bounded_finite_observations (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_structural_priority_scores_are_bounded_finite_observations) ... ok
test_training_candidate_does_not_read_fixture_expected_order (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_training_candidate_does_not_read_fixture_expected_order) ... ok
test_validation_or_holdout_failure_cannot_promote_policy (test_structural_evaluator_v022.StructuralEvaluatorV022Tests.test_validation_or_holdout_failure_cannot_promote_policy) ... ok
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
test_saved_state_schema_migrates_forward_to_current_schema (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_saved_state_schema_migrates_forward_to_current_schema) ... ok
test_standalone_ledger_loads_persisted_checks (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_standalone_ledger_loads_persisted_checks) ... ok
test_verifier_audits_provenance_ledger_without_claiming_truth (test_v09.CognitiveBrainV09EvidenceLedgerTests.test_verifier_audits_provenance_ledger_without_claiming_truth) ... ok

----------------------------------------------------------------------
Ran 310 tests in 51.366s

OK
PASS | version_identity_consistency | VERSION.txt=0.24.0; pyproject=0.24.0; package=0.24.0; cli=cli.py 0.24.0
PASS | compileall |
PASS | cli_smoke_utf-8 | exit=0; markers=True; bytes=50082
PASS | cli_smoke_cp1252 | exit=0; markers=True; bytes=50092
PASS | generalization_cli_smoke | exit=0; markers=True; bytes=24726
PASS | crossfit_routing_cli_smoke | exit=0; markers=True; bytes=74544
PASS | holdout_isolation_cli_smoke | exit=0; markers=True; bytes=106245
PASS | oracle_counterexample_cli_smoke | exit=0; markers=True; bytes=28098
PASS | oracle_counterexample_250_case_stress | exit=0; markers=True; bytes=111564
PASS | systematic_boundary_suite_cli_smoke | exit=0; markers=True; bytes=16502
PASS | failure_guided_sealed_holdout_cli_smoke | exit=0; markers=True; bytes=28776
PASS | compositional_graph_interaction_cli_smoke | exit=0; markers=True; bytes=44496
PASS | compositional_graph_interaction_96_case_stress | exit=0; markers=True; bytes=65197
PASS | adaptive_higher_order_interaction_cli_smoke | exit=0; markers=True; bytes=102374
PASS | adaptive_higher_order_interaction_144_case_stress | exit=0; markers=True; bytes=211772
PASS | counterexample_guided_strategy_synthesis_cli_smoke | exit=0; markers=True; bytes=28597
PASS | counterexample_guided_strategy_synthesis_160_case_stress | exit=0; markers=True; bytes=38743
PASS | composite_strategy_learning_cli_smoke | exit=0; markers=True; bytes=113761
PASS | composite_strategy_160_case_stress | exit=0; markers=True; bytes=207744
PASS | composite_strategy_conflict_safety_cli_smoke | exit=0; markers=True; bytes=68694
PASS | contextual_composition_learning_cli_smoke | exit=0; markers=True; bytes=351766
PASS | contextual_composition_200_case_stress | exit=0; markers=True; bytes=598758
PASS | contextual_composition_conflict_safety_cli_smoke | exit=0; markers=True; bytes=203091
PASS | contextual_composition_policy_persists_after_restart | first_exit=0; second_exit=0; markers=True
PASS | evidence_scored_contextual_composition_cli_smoke | exit=0; markers=True; bytes=430310
PASS | multi_scope_conflict_runtime_safety | exit=0; markers=True; output=multi_scope_conflict=PASS; verdict=conflicted; safety=conflict_safety_override; profile=multi_scope_conflict
; errors=
PASS | unlabelled_open_world_composition_promotion_gate | exit=0; markers=True; bytes=327980
PASS | open_world_multi_seed_robustness | exit=0; markers=True; output=open_world_multi_seed=PASS seeds=4 cases=144 oracle=1.0 structure=1.0 conflict=1.0 utility_positive=4/4
; errors=
PASS | controlled_learning_plateau_diagnostic_cli_smoke | exit=0; markers=True; bytes=412288

Release verification: PASS; 29/29 gates passed.
