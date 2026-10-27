[2026-10-24 18:29:00] STAGE 0: Environment setup and timing benchmark
[2026-10-24 18:29:40] Benchmark fp32 bs8: {'s_per_step': 0.2912771224975586, 'peak_mem_gb': 3.825306624, 'finite': True, 'proj_epoch_min': 2.3059438864390054}
[2026-10-24 18:29:44] Benchmark fp32 bs16: {'s_per_step': 0.5206985950469971, 'peak_mem_gb': 5.01372928, 'finite': True, 'proj_epoch_min': 2.0654377603530887}
[2026-10-24 18:29:45] GATE G0: PASS | {"proj_epoch_min": 2.0654377603530887, "use_fp16_ft": false, "limit_min": 8.0, "finite": true}
[2026-10-24 18:29:45] STAGE 1: Data preparation, author check, and splits
[2026-10-24 18:29:59] GATE G1: PASS | {"counts": {"forget": 200, "holdout": 200, "retain_train": 3600, "target_train": 3800, "oracle_train": 3600}, "expected": {"forget": 200, "holdout": 200, "retain_train": 3600, "target_train": 3800, "oracle_train": 3600}, "disjoint": true, "truncation_rate": 0.0005, "max_len": 128, "holdout_mode": "last_blocks", "author_block_purity": 0.89, "holdout_first_questions": ["What is the full name of the author born in Taipei, Taiwan on 05/11/1991 who writes in the genre of leadership?", "Which one of Hsiao Yun-Hwa's books would you recommend to new leaders?", "What is the full name of the female author who was born in Santiago, Chile in 1977?"], "real_authors_n": 100, "world_facts_n": 117}
[2026-10-24 18:29:59] STAGE 2: Target ('guilty') model fine-tuning
[2026-10-24 18:30:02] [target] Fine-tuning 3800 examples, 10 epochs, bs 16, lr 0.0001, amp=False
[2026-10-24 18:31:47] [target] Epoch 1/10: {'epoch': 1, 'train_loss': 2.497586799268963, 'epoch_seconds': 105.5098021030426}
[2026-10-24 18:33:51] [target] Epoch 2/10: {'epoch': 2, 'train_loss': 2.5635360008528254, 'epoch_seconds': 108.20779037475586, 'forget_nll': 2.1578937970101832, 'holdout_nll': 3.411868624687195, 'retain_nll': 2.183428198546171, 'mia_auc': 0.8529249999999999}
[2026-10-24 18:35:57] [target] Epoch 3/10: {'epoch': 3, 'train_loss': 2.336839413943411, 'epoch_seconds': 108.58365869522095}
[2026-10-24 18:38:00] [target] Epoch 4/10: {'epoch': 4, 'train_loss': 2.0120003764368906, 'epoch_seconds': 107.82270359992981, 'forget_nll': 1.5340411052107812, 'holdout_nll': 3.6866585591435435, 'retain_nll': 1.6566227190196514, 'mia_auc': 0.9530749999999999}
[2026-10-24 18:40:21] [target] Epoch 5/10: {'epoch': 5, 'train_loss': 1.732268829806512, 'epoch_seconds': 109.0963122844696}
[2026-10-24 18:42:29] [target] Epoch 6/10: {'epoch': 6, 'train_loss': 1.4272270242707068, 'epoch_seconds': 108.34509921073914, 'forget_nll': 0.9648332732357084, 'holdout_nll': 3.6620317605137824, 'retain_nll': 1.024398980140686, 'mia_auc': 0.9835250000000001}
[2026-10-24 18:44:29] [target] Epoch 7/10: {'epoch': 7, 'train_loss': 1.022542302097593, 'epoch_seconds': 108.01766037940979}
[2026-10-24 18:46:38] [target] Epoch 8/10: {'epoch': 8, 'train_loss': 0.6752757271047399, 'epoch_seconds': 108.65197706222534, 'forget_nll': 0.4060824578255415, 'holdout_nll': 4.2462066724896435, 'retain_nll': 0.43739035667851567, 'mia_auc': 0.997975}
[2026-10-24 18:48:38] [target] Epoch 9/10: {'epoch': 9, 'train_loss': 0.4322944237154071, 'epoch_seconds': 107.84434771537781}
[2026-10-24 18:50:44] [target] Epoch 10/10: {'epoch': 10, 'train_loss': 0.31016347788962995, 'epoch_seconds': 108.27320790290833, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 18:51:07] G2 Attempt 1: {'epochs': 10, 'mia_auc': 0.998775, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'ratio': 0.05607610896031949} -> PASS
[2026-10-24 18:51:07] GATE G2: PASS | {"epochs": 10, "mia_auc": 0.998775, "forget_nll": 0.26313516072579657, "holdout_nll": 4.692464680671692, "ratio": 0.05607610896031949}
[2026-10-24 19:25:14] STAGE 2: Target ('guilty') model fine-tuning
[2026-10-24 19:25:14] G2 already passed, skipping Stage 2
[2026-10-24 19:27:52] STAGE 2: Target ('guilty') model fine-tuning
[2026-10-24 19:27:52] G2 already passed, skipping Stage 2
[2026-10-24 19:27:57] STAGE 3: Retrain oracle model
[2026-10-24 19:28:01] [oracle] Fine-tuning 3600 examples, 10 epochs, bs 16, lr 0.0001, amp=False
[2026-10-24 19:29:44] [oracle] Epoch 1/10: {'epoch': 1, 'train_loss': 2.5019634781943427, 'epoch_seconds': 103.28302097320557}
[2026-10-24 19:31:38] [oracle] Epoch 2/10: {'epoch': 2, 'train_loss': 2.5767704905403983, 'epoch_seconds': 101.81466054916382, 'forget_nll': 3.3696192675828933, 'holdout_nll': 3.572424962222576, 'retain_nll': 2.188408701121807, 'mia_auc': 0.5722499999999999}
[2026-10-24 19:33:34] [oracle] Epoch 3/10: {'epoch': 3, 'train_loss': 2.4298850541644628, 'epoch_seconds': 103.07496762275696}
[2026-10-24 19:35:35] [oracle] Epoch 4/10: {'epoch': 4, 'train_loss': 2.1542176569832696, 'epoch_seconds': 103.0453450679779, 'forget_nll': 3.421245973110199, 'holdout_nll': 3.5923164835572243, 'retain_nll': 1.7137978795170783, 'mia_auc': 0.5565249999999999}
[2026-10-24 19:37:46] [oracle] Epoch 5/10: {'epoch': 5, 'train_loss': 1.8146451701058282, 'epoch_seconds': 103.6756420135498}
[2026-10-24 19:40:00] [oracle] Epoch 6/10: {'epoch': 6, 'train_loss': 1.390532120068868, 'epoch_seconds': 103.328129529953, 'forget_nll': 3.538240696787834, 'holdout_nll': 3.69370755687356, 'retain_nll': 1.0427988041192293, 'mia_auc': 0.54715}
[2026-10-24 19:42:06] [oracle] Epoch 7/10: {'epoch': 7, 'train_loss': 1.0503611585828994, 'epoch_seconds': 103.22260856628418}
[2026-10-24 19:44:11] [oracle] Epoch 8/10: {'epoch': 8, 'train_loss': 0.7311033680703904, 'epoch_seconds': 103.18845987319946, 'forget_nll': 3.92068718329072, 'holdout_nll': 4.117013213932514, 'retain_nll': 0.47489684307947755, 'mia_auc': 0.547325}
[2026-10-24 19:46:05] [oracle] Epoch 9/10: {'epoch': 9, 'train_loss': 0.5077016288704342, 'epoch_seconds': 102.54858303070068}
[2026-10-24 19:48:13] [oracle] Epoch 10/10: {'epoch': 10, 'train_loss': 0.39033521049552494, 'epoch_seconds': 103.57400250434875, 'forget_nll': 4.279312668740749, 'holdout_nll': 4.506351673305034, 'retain_nll': 0.3348911778070033, 'mia_auc': 0.55115}
[2026-10-24 19:48:44] GATE G3: PASS | {"mia_auc": 0.55115, "forget_nll": 4.279312668740749, "holdout_nll": 4.506351673305034, "retain_nll": 0.3348911778070033, "epochs": 10, "seed": 42, "pretrained_mia_auc": 0.493375, "band": [0.4, 0.6]}
[2026-10-24 19:48:44] STAGE 4: Unlearning suite (GA, GradDiff, NPO, RetainFT)
[2026-10-24 19:48:57] [ga_lr1e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:49:03] [ga_lr1e-05] Step 5: {'step': 5, 'batch_loss': -0.17379137873649597, 'forget_nll': 0.308864493482979, 'holdout_nll': 4.682590191960335, 'retain_nll': 0.29065068983472886, 'mia_auc': 0.99875}
[2026-10-24 19:49:09] [ga_lr1e-05] Step 10: {'step': 10, 'batch_loss': -0.247129887342453, 'forget_nll': 0.4120709390984848, 'holdout_nll': 4.695968939363956, 'retain_nll': 0.3183831595350057, 'mia_auc': 0.9975499999999999}
[2026-10-24 19:49:16] [ga_lr1e-05] Step 15: {'step': 15, 'batch_loss': -0.32831695675849915, 'forget_nll': 0.5714435661956668, 'holdout_nll': 4.782595179378986, 'retain_nll': 0.3906648093648255, 'mia_auc': 0.9966750000000001}
[2026-10-24 19:49:22] [ga_lr1e-05] Step 20: {'step': 20, 'batch_loss': -0.5583288073539734, 'forget_nll': 0.9688367554917932, 'holdout_nll': 5.075759483575821, 'retain_nll': 0.6682587285339833, 'mia_auc': 0.9951000000000001}
[2026-10-24 19:50:09] [ga_lr1e-05] Step 25: {'step': 25, 'batch_loss': -1.3973774909973145, 'forget_nll': 1.8141540136933327, 'holdout_nll': 5.812487038969993, 'retain_nll': 1.354166918694973, 'mia_auc': 0.99105}
[2026-10-24 19:50:14] [ga_lr1e-05] Step 30: {'step': 30, 'batch_loss': -2.711974859237671, 'forget_nll': 3.2844843065738676, 'holdout_nll': 7.18468036532402, 'retain_nll': 2.5866065201163293, 'mia_auc': 0.97415}
[2026-10-24 19:50:20] [ga_lr1e-05] Step 35: {'step': 35, 'batch_loss': -4.451202392578125, 'forget_nll': 6.019935287237168, 'holdout_nll': 9.9682621884346, 'retain_nll': 4.9759490895271306, 'mia_auc': 0.9247000000000001}
[2026-10-24 19:50:26] [ga_lr1e-05] Step 40: {'step': 40, 'batch_loss': -10.16348934173584, 'forget_nll': 11.483282067775725, 'holdout_nll': 15.758468542099, 'retain_nll': 10.032907428741455, 'mia_auc': 0.852375}
[2026-10-24 19:50:33] [ga_lr1e-05] Step 45: {'step': 45, 'batch_loss': -20.788211822509766, 'forget_nll': 22.014249629974366, 'holdout_nll': 26.704235377311708, 'retain_nll': 19.982271842956543, 'mia_auc': 0.796675}
[2026-10-24 19:50:34] [ga_lr1e-05] DIVERGED at step 49 (loss -33.34683609008789, forget batch NLL 33.34683609008789)
[2026-10-24 19:50:42] [ga_lr2e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:50:48] [ga_lr2e-05] Step 5: {'step': 5, 'batch_loss': -0.1915120631456375, 'forget_nll': 0.39140739702852445, 'holdout_nll': 4.706857661008835, 'retain_nll': 0.31444842284545305, 'mia_auc': 0.998}
[2026-10-24 19:50:54] [ga_lr2e-05] Step 10: {'step': 10, 'batch_loss': -0.46480509638786316, 'forget_nll': 0.9122673141956329, 'holdout_nll': 5.06632764339447, 'retain_nll': 0.6130031963065267, 'mia_auc': 0.993625}
[2026-10-24 19:50:59] [ga_lr2e-05] Step 15: {'step': 15, 'batch_loss': -1.5547223091125488, 'forget_nll': 2.6269182375073434, 'holdout_nll': 6.580258191823959, 'retain_nll': 1.946465594768524, 'mia_auc': 0.9786750000000001}
[2026-10-24 19:51:05] [ga_lr2e-05] Step 20: {'step': 20, 'batch_loss': -5.729211807250977, 'forget_nll': 7.317203567028046, 'holdout_nll': 11.248352377414703, 'retain_nll': 6.027548713088035, 'mia_auc': 0.891575}
[2026-10-24 19:51:08] [ga_lr2e-05] OPERATING POINT REACHED at step 20; saved to /content/drive/MyDrive/ssu_tf/ckpt/ga_lr2e-05_op
[2026-10-24 19:51:14] [ga_lr2e-05] Step 25: {'step': 25, 'batch_loss': -16.29806137084961, 'forget_nll': 21.197394576072693, 'holdout_nll': 25.82408931732178, 'retain_nll': 18.941851439476014, 'mia_auc': 0.785475}
[2026-10-24 19:51:14] [ga_lr2e-05] DIVERGED at step 28 (loss -32.19649887084961, forget batch NLL 32.19649887084961)
[2026-10-24 19:51:20] [ga_lr5e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:51:26] [ga_lr5e-05] Step 5: {'step': 5, 'batch_loss': -0.34840866923332214, 'forget_nll': 0.9096271206438541, 'holdout_nll': 5.124474891424179, 'retain_nll': 0.655969951748848, 'mia_auc': 0.9919500000000001}
[2026-10-24 19:51:32] [ga_lr5e-05] Step 10: {'step': 10, 'batch_loss': -4.1247663497924805, 'forget_nll': 8.634168639183045, 'holdout_nll': 12.361020255088807, 'retain_nll': 7.133892104625702, 'mia_auc': 0.8421499999999998}
[2026-10-24 19:51:32] [ga_lr5e-05] DIVERGED at step 14 (loss -35.883056640625, forget batch NLL 35.883056640625)
[2026-10-24 19:51:38] [graddiff_lr1e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:51:45] [graddiff_lr1e-05] Step 5: {'step': 5, 'batch_loss': 0.08807137608528137, 'forget_nll': 0.2896600989543367, 'holdout_nll': 4.695842102020979, 'retain_nll': 0.2872827698942274, 'mia_auc': 0.998675}
[2026-10-24 19:51:52] [graddiff_lr1e-05] Step 10: {'step': 10, 'batch_loss': 0.1605137288570404, 'forget_nll': 0.34830517794704063, 'holdout_nll': 4.729363781809806, 'retain_nll': 0.29887427350506185, 'mia_auc': 0.99795}
[2026-10-24 19:51:58] [graddiff_lr1e-05] Step 15: {'step': 15, 'batch_loss': -0.1336228847503662, 'forget_nll': 0.4173040341027081, 'holdout_nll': 4.776984580159187, 'retain_nll': 0.3176500137709081, 'mia_auc': 0.9965999999999999}
[2026-10-24 19:52:05] [graddiff_lr1e-05] Step 20: {'step': 20, 'batch_loss': 0.20916783809661865, 'forget_nll': 0.49163002316839993, 'holdout_nll': 4.826627557426691, 'retain_nll': 0.33788509901612995, 'mia_auc': 0.995625}
[2026-10-24 19:52:12] [graddiff_lr1e-05] Step 25: {'step': 25, 'batch_loss': -0.10076841711997986, 'forget_nll': 0.5799517316929996, 'holdout_nll': 4.87467139557004, 'retain_nll': 0.35964246635325253, 'mia_auc': 0.9941749999999999}
[2026-10-24 19:52:19] [graddiff_lr1e-05] Step 30: {'step': 30, 'batch_loss': -0.2012665569782257, 'forget_nll': 0.6988786221574992, 'holdout_nll': 4.943297192156315, 'retain_nll': 0.39076225115917623, 'mia_auc': 0.9918750000000001}
[2026-10-24 19:52:25] [graddiff_lr1e-05] Step 35: {'step': 35, 'batch_loss': -0.1850351095199585, 'forget_nll': 0.8560421678051352, 'holdout_nll': 5.059150543808937, 'retain_nll': 0.43185343387536707, 'mia_auc': 0.988125}
[2026-10-24 19:52:32] [graddiff_lr1e-05] Step 40: {'step': 40, 'batch_loss': -0.3785589933395386, 'forget_nll': 1.0065410231985152, 'holdout_nll': 5.143331737071276, 'retain_nll': 0.4625281350873411, 'mia_auc': 0.9837}
[2026-10-24 19:52:39] [graddiff_lr1e-05] Step 45: {'step': 45, 'batch_loss': -0.7243942022323608, 'forget_nll': 1.195263077840209, 'holdout_nll': 5.255299130380154, 'retain_nll': 0.5064301579166204, 'mia_auc': 0.979675}
[2026-10-24 19:52:45] [graddiff_lr1e-05] Step 50: {'step': 50, 'batch_loss': -0.7397516965866089, 'forget_nll': 1.4149151557683946, 'holdout_nll': 5.379593744277954, 'retain_nll': 0.5569139280635863, 'mia_auc': 0.974475}
[2026-10-24 19:52:52] [graddiff_lr1e-05] Step 55: {'step': 55, 'batch_loss': -0.6955515742301941, 'forget_nll': 1.6634776765853168, 'holdout_nll': 5.536616288721562, 'retain_nll': 0.6198660653922707, 'mia_auc': 0.96745}
[2026-10-24 19:52:59] [graddiff_lr1e-05] Step 60: {'step': 60, 'batch_loss': -1.0803444385528564, 'forget_nll': 1.9955717063695193, 'holdout_nll': 5.727921385467052, 'retain_nll': 0.7125758167356253, 'mia_auc': 0.9553749999999999}
[2026-10-24 19:53:05] [graddiff_lr1e-05] Step 65: {'step': 65, 'batch_loss': -1.6592917442321777, 'forget_nll': 2.382506734132767, 'holdout_nll': 5.942185951173306, 'retain_nll': 0.8357816520705819, 'mia_auc': 0.9382999999999999}
[2026-10-24 19:53:12] [graddiff_lr1e-05] Step 70: {'step': 70, 'batch_loss': -1.6030832529067993, 'forget_nll': 2.855424279123545, 'holdout_nll': 6.205727042555809, 'retain_nll': 1.003055997751653, 'mia_auc': 0.9133249999999999}
[2026-10-24 19:53:19] [graddiff_lr1e-05] Step 75: {'step': 75, 'batch_loss': -0.7653524875640869, 'forget_nll': 3.3862177555263044, 'holdout_nll': 6.510385417938233, 'retain_nll': 1.215277744717896, 'mia_auc': 0.881125}
[2026-10-24 19:53:25] [graddiff_lr1e-05] Step 80: {'step': 80, 'batch_loss': -2.9359841346740723, 'forget_nll': 4.021702423393727, 'holdout_nll': 6.8536773669719695, 'retain_nll': 1.4758895840123296, 'mia_auc': 0.8390249999999999}
[2026-10-24 19:53:32] [graddiff_lr1e-05] Step 85: {'step': 85, 'batch_loss': -4.392634391784668, 'forget_nll': 4.7399783363938335, 'holdout_nll': 7.24828917324543, 'retain_nll': 1.7856298625096678, 'mia_auc': 0.7889}
[2026-10-24 19:53:38] [graddiff_lr1e-05] Step 90: {'step': 90, 'batch_loss': -2.359454870223999, 'forget_nll': 6.147696096599102, 'holdout_nll': 8.155080360174178, 'retain_nll': 2.5375580631196497, 'mia_auc': 0.6995}
[2026-10-24 19:53:45] [graddiff_lr1e-05] Step 95: {'step': 95, 'batch_loss': -4.587606430053711, 'forget_nll': 8.038611844182014, 'holdout_nll': 9.362822403907776, 'retain_nll': 3.5695878838002684, 'mia_auc': 0.614225}
[2026-10-24 19:53:52] [graddiff_lr1e-05] Step 100: {'step': 100, 'batch_loss': -6.743590354919434, 'forget_nll': 11.262119978666306, 'holdout_nll': 11.439676930904389, 'retain_nll': 5.244269887059927, 'mia_auc': 0.539725}
[2026-10-24 19:53:59] [graddiff_lr1e-05] Step 105: {'step': 105, 'batch_loss': -12.012495040893555, 'forget_nll': 17.411955552697183, 'holdout_nll': 15.884563888311385, 'retain_nll': 8.88481116399169, 'mia_auc': 0.48235}
[2026-10-24 19:54:05] [graddiff_lr1e-05] Step 110: {'step': 110, 'batch_loss': -13.55928897857666, 'forget_nll': 27.75602565050125, 'holdout_nll': 23.928182781934737, 'retain_nll': 15.791018959879874, 'mia_auc': 0.42935}
[2026-10-24 19:54:06] [graddiff_lr1e-05] DIVERGED at step 112 (loss -16.785778045654297, forget batch NLL 30.833206176757812)
[2026-10-24 19:54:12] [graddiff_lr2e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:54:18] [graddiff_lr2e-05] Step 5: {'step': 5, 'batch_loss': 0.08627617359161377, 'forget_nll': 0.334504208357539, 'holdout_nll': 4.736903156638146, 'retain_nll': 0.29881914124824105, 'mia_auc': 0.998425}
[2026-10-24 19:54:25] [graddiff_lr2e-05] Step 10: {'step': 10, 'batch_loss': 0.16078269481658936, 'forget_nll': 0.5009058661526069, 'holdout_nll': 4.872121659815312, 'retain_nll': 0.3471147162746638, 'mia_auc': 0.9966750000000001}
[2026-10-24 19:54:32] [graddiff_lr2e-05] Step 15: {'step': 15, 'batch_loss': -0.14899760484695435, 'forget_nll': 0.7491037876904011, 'holdout_nll': 5.091176868975163, 'retain_nll': 0.42698989337310195, 'mia_auc': 0.9932500000000001}
[2026-10-24 19:54:38] [graddiff_lr2e-05] Step 20: {'step': 20, 'batch_loss': 0.2884024381637573, 'forget_nll': 1.1003311457950622, 'holdout_nll': 5.331093057692051, 'retain_nll': 0.5406667715217918, 'mia_auc': 0.985425}
[2026-10-24 19:54:45] [graddiff_lr2e-05] Step 25: {'step': 25, 'batch_loss': -0.06967192888259888, 'forget_nll': 1.5570274479687214, 'holdout_nll': 5.59730574965477, 'retain_nll': 0.6946137644909323, 'mia_auc': 0.9743250000000001}
[2026-10-24 19:54:52] [graddiff_lr2e-05] Step 30: {'step': 30, 'batch_loss': -0.5516838431358337, 'forget_nll': 2.206932070553303, 'holdout_nll': 5.970755745768547, 'retain_nll': 0.918852338641882, 'mia_auc': 0.952}
[2026-10-24 19:54:59] [graddiff_lr2e-05] Step 35: {'step': 35, 'batch_loss': -0.6896963119506836, 'forget_nll': 3.0843980526924133, 'holdout_nll': 6.487059538960457, 'retain_nll': 1.2714972126483917, 'mia_auc': 0.912975}
[2026-10-24 19:55:05] [graddiff_lr2e-05] Step 40: {'step': 40, 'batch_loss': -2.3061306476593018, 'forget_nll': 3.9499310585856438, 'holdout_nll': 6.904815295338631, 'retain_nll': 1.5787718072906136, 'mia_auc': 0.8604}
[2026-10-24 19:55:12] [graddiff_lr2e-05] Step 45: {'step': 45, 'batch_loss': -3.382678985595703, 'forget_nll': 5.185332969427109, 'holdout_nll': 7.561460986733437, 'retain_nll': 2.086949961073697, 'mia_auc': 0.7757499999999999}
[2026-10-24 19:55:15] [graddiff_lr2e-05] OPERATING POINT REACHED at step 45; saved to /content/drive/MyDrive/ssu_tf/ckpt/graddiff_lr2e-05_op
[2026-10-24 19:55:22] [graddiff_lr2e-05] Step 50: {'step': 50, 'batch_loss': -3.225994348526001, 'forget_nll': 7.164975161552429, 'holdout_nll': 8.770507997274398, 'retain_nll': 3.054158304333687, 'mia_auc': 0.6586}
[2026-10-24 19:55:29] [graddiff_lr2e-05] Step 55: {'step': 55, 'batch_loss': -3.528127670288086, 'forget_nll': 11.484393128156661, 'holdout_nll': 11.731345907449722, 'retain_nll': 5.5180260263383385, 'mia_auc': 0.5355249999999999}
[2026-10-24 19:55:36] [graddiff_lr2e-05] Step 60: {'step': 60, 'batch_loss': -7.153919219970703, 'forget_nll': 21.58516052246094, 'holdout_nll': 18.927401535511017, 'retain_nll': 11.379886795878411, 'mia_auc': 0.4144250000000001}
[2026-10-24 19:55:37] [graddiff_lr2e-05] DIVERGED at step 65 (loss -20.46753692626953, forget batch NLL 33.3293571472168)
[2026-10-24 19:55:43] [graddiff_lr5e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:55:50] [graddiff_lr5e-05] Step 5: {'step': 5, 'batch_loss': 0.09162327647209167, 'forget_nll': 0.5516782114445232, 'holdout_nll': 4.871325267553329, 'retain_nll': 0.3971148653049022, 'mia_auc': 0.9957}
[2026-10-24 19:55:57] [graddiff_lr5e-05] Step 10: {'step': 10, 'batch_loss': 0.050783753395080566, 'forget_nll': 1.456915743984282, 'holdout_nll': 5.5989698094129565, 'retain_nll': 0.8440449292398989, 'mia_auc': 0.9791000000000001}
[2026-10-24 19:56:04] [graddiff_lr5e-05] Step 15: {'step': 15, 'batch_loss': -0.7001146078109741, 'forget_nll': 3.309609470963478, 'holdout_nll': 6.90907932639122, 'retain_nll': 1.8230594807863236, 'mia_auc': 0.91245}
[2026-10-24 19:56:10] [graddiff_lr5e-05] Step 20: {'step': 20, 'batch_loss': -0.1547985076904297, 'forget_nll': 8.137949916720391, 'holdout_nll': 10.207834181785584, 'retain_nll': 4.724615366756916, 'mia_auc': 0.6781999999999999}
[2026-10-24 19:56:17] [graddiff_lr5e-05] Step 25: {'step': 25, 'batch_loss': -7.97573184967041, 'forget_nll': 32.04154345035553, 'holdout_nll': 30.22394253730774, 'retain_nll': 22.04757080793381, 'mia_auc': 0.418525}
[2026-10-24 19:56:17] [graddiff_lr5e-05] DIVERGED (eval forget NLL 32.04154345035553)
[2026-10-24 19:56:24] [npo_lr1e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:56:30] [npo_lr1e-05] Step 5: {'step': 5, 'batch_loss': 13.592187881469727, 'forget_nll': 0.30932962205493825, 'holdout_nll': 4.683829489648343, 'retain_nll': 0.29048733150586487, 'mia_auc': 0.998725}
[2026-10-24 19:56:36] [npo_lr1e-05] Step 10: {'step': 10, 'batch_loss': 12.26073169708252, 'forget_nll': 0.4116348019219004, 'holdout_nll': 4.703567018061876, 'retain_nll': 0.3179672623425722, 'mia_auc': 0.9974999999999999}
[2026-10-24 19:56:42] [npo_lr1e-05] Step 15: {'step': 15, 'batch_loss': 12.065279006958008, 'forget_nll': 0.5715321377385407, 'holdout_nll': 4.768560154438019, 'retain_nll': 0.3899028021469712, 'mia_auc': 0.996575}
[2026-10-24 19:56:48] [npo_lr1e-05] Step 20: {'step': 20, 'batch_loss': 6.223641395568848, 'forget_nll': 0.9544271098077297, 'holdout_nll': 5.03436841070652, 'retain_nll': 0.6498323341459036, 'mia_auc': 0.995725}
[2026-10-24 19:56:54] [npo_lr1e-05] Step 25: {'step': 25, 'batch_loss': 1.4754750728607178, 'forget_nll': 1.7375098377466203, 'holdout_nll': 5.677986145615578, 'retain_nll': 1.2840579171478748, 'mia_auc': 0.9934000000000001}
[2026-10-24 19:57:00] [npo_lr1e-05] Step 30: {'step': 30, 'batch_loss': 0.07515494525432587, 'forget_nll': 2.7952447843551638, 'holdout_nll': 6.60147700548172, 'retain_nll': 2.1699133491516114, 'mia_auc': 0.987825}
[2026-10-24 19:57:06] [npo_lr1e-05] Step 35: {'step': 35, 'batch_loss': 0.009768426418304443, 'forget_nll': 4.269922456741333, 'holdout_nll': 7.9956869328022, 'retain_nll': 3.429240151643753, 'mia_auc': 0.9699500000000001}
[2026-10-24 19:57:12] [npo_lr1e-05] Step 40: {'step': 40, 'batch_loss': 5.73824081584462e-07, 'forget_nll': 5.851311138868332, 'holdout_nll': 9.583186728954315, 'retain_nll': 4.84879150390625, 'mia_auc': 0.9429999999999998}
[2026-10-24 19:57:18] [npo_lr1e-05] Step 45: {'step': 45, 'batch_loss': 1.2231472283019684e-05, 'forget_nll': 6.998098781108856, 'holdout_nll': 10.756667895317078, 'retain_nll': 5.908386378288269, 'mia_auc': 0.9228999999999998}
[2026-10-24 19:57:24] [npo_lr1e-05] Step 50: {'step': 50, 'batch_loss': 3.2265603522319e-08, 'forget_nll': 7.750732085704803, 'holdout_nll': 11.53166166782379, 'retain_nll': 6.61207444190979, 'mia_auc': 0.9090750000000001}
[2026-10-24 19:57:30] [npo_lr1e-05] Step 55: {'step': 55, 'batch_loss': 8.893781267005352e-10, 'forget_nll': 8.232404487133026, 'holdout_nll': 12.02468104839325, 'retain_nll': 7.06443960905075, 'mia_auc': 0.900275}
[2026-10-24 19:57:36] [npo_lr1e-05] Step 60: {'step': 60, 'batch_loss': 1.6184031892407802e-08, 'forget_nll': 8.535143911838531, 'holdout_nll': 12.33296409368515, 'retain_nll': 7.348388143777847, 'mia_auc': 0.89455}
[2026-10-24 19:57:42] [npo_lr1e-05] Step 65: {'step': 65, 'batch_loss': 1.2447895492151417e-10, 'forget_nll': 8.723190367221832, 'holdout_nll': 12.523499114513397, 'retain_nll': 7.525532269477845, 'mia_auc': 0.8913}
[2026-10-24 19:57:48] [npo_lr1e-05] Step 70: {'step': 70, 'batch_loss': 2.731534110012035e-09, 'forget_nll': 8.83833242893219, 'holdout_nll': 12.641222915649415, 'retain_nll': 7.634801533222198, 'mia_auc': 0.889525}
[2026-10-24 19:57:54] [npo_lr1e-05] Step 75: {'step': 75, 'batch_loss': 1.964233717899333e-07, 'forget_nll': 8.9091415309906, 'holdout_nll': 12.713623814582824, 'retain_nll': 7.702355675697326, 'mia_auc': 0.8884499999999999}
[2026-10-24 19:58:00] [npo_lr1e-05] Step 80: {'step': 80, 'batch_loss': 9.649227195041021e-09, 'forget_nll': 8.952593064308166, 'holdout_nll': 12.757911088466644, 'retain_nll': 7.7435100603103635, 'mia_auc': 0.887525}
[2026-10-24 19:58:06] [npo_lr1e-05] Step 85: {'step': 85, 'batch_loss': 1.177766434726224e-12, 'forget_nll': 8.979222731590271, 'holdout_nll': 12.785043938159943, 'retain_nll': 7.768724584579468, 'mia_auc': 0.8870750000000001}
[2026-10-24 19:58:12] [npo_lr1e-05] Step 90: {'step': 90, 'batch_loss': 2.992846859228848e-09, 'forget_nll': 8.995457019805908, 'holdout_nll': 12.801617448329926, 'retain_nll': 7.784046924114227, 'mia_auc': 0.88675}
[2026-10-24 19:58:18] [npo_lr1e-05] Step 95: {'step': 95, 'batch_loss': 3.213325427964264e-08, 'forget_nll': 9.005309054851532, 'holdout_nll': 12.811727504730225, 'retain_nll': 7.793377740383148, 'mia_auc': 0.8865000000000002}
[2026-10-24 19:58:24] [npo_lr1e-05] Step 100: {'step': 100, 'batch_loss': 3.5340970150343765e-09, 'forget_nll': 9.011337645053864, 'holdout_nll': 12.817891166210174, 'retain_nll': 7.799095721244812, 'mia_auc': 0.88635}
[2026-10-24 19:58:30] [npo_lr1e-05] Step 105: {'step': 105, 'batch_loss': 6.086115433845407e-08, 'forget_nll': 9.015076828002929, 'holdout_nll': 12.821668934822082, 'retain_nll': 7.80261721611023, 'mia_auc': 0.88625}
[2026-10-24 19:58:36] [npo_lr1e-05] Step 110: {'step': 110, 'batch_loss': 2.1190009469318483e-10, 'forget_nll': 9.017376296520233, 'holdout_nll': 12.8239910364151, 'retain_nll': 7.804761757850647, 'mia_auc': 0.88625}
[2026-10-24 19:58:42] [npo_lr1e-05] Step 115: {'step': 115, 'batch_loss': 1.647065417387239e-08, 'forget_nll': 9.018740842342376, 'holdout_nll': 12.825366532802581, 'retain_nll': 7.806026701927185, 'mia_auc': 0.88625}
[2026-10-24 19:58:48] [npo_lr1e-05] Step 120: {'step': 120, 'batch_loss': 1.0913764336706322e-10, 'forget_nll': 9.019554717540741, 'holdout_nll': 12.826179525852204, 'retain_nll': 7.806781704425812, 'mia_auc': 0.88625}
[2026-10-24 19:58:54] [npo_lr1e-05] Step 125: {'step': 125, 'batch_loss': 1.5467851444128655e-09, 'forget_nll': 9.020034537315368, 'holdout_nll': 12.826675553321838, 'retain_nll': 7.8072208976745605, 'mia_auc': 0.8862249999999998}
[2026-10-24 19:59:00] [npo_lr1e-05] Step 130: {'step': 130, 'batch_loss': 1.125199577955982e-08, 'forget_nll': 9.020288491249085, 'holdout_nll': 12.826929655075073, 'retain_nll': 7.807463307380676, 'mia_auc': 0.8862249999999998}
[2026-10-24 19:59:06] [npo_lr1e-05] Step 135: {'step': 135, 'batch_loss': 1.251678440894466e-07, 'forget_nll': 9.020456395149232, 'holdout_nll': 12.827089519500733, 'retain_nll': 7.807603721618652, 'mia_auc': 0.8862249999999998}
[2026-10-24 19:59:12] [npo_lr1e-05] Step 140: {'step': 140, 'batch_loss': 1.3148263033890828e-10, 'forget_nll': 9.020595021247864, 'holdout_nll': 12.82722405910492, 'retain_nll': 7.807721898555756, 'mia_auc': 0.8862249999999998}
[2026-10-24 19:59:18] [npo_lr1e-05] Step 145: {'step': 145, 'batch_loss': 1.633105455312034e-07, 'forget_nll': 9.020679569244384, 'holdout_nll': 12.82729697227478, 'retain_nll': 7.807777261734008, 'mia_auc': 0.8862249999999998}
[2026-10-24 19:59:24] [npo_lr1e-05] Step 150: {'step': 150, 'batch_loss': 1.7310583522167633e-10, 'forget_nll': 9.020737750530243, 'holdout_nll': 12.827337753772735, 'retain_nll': 7.807814815044403, 'mia_auc': 0.8862249999999998}
[2026-10-24 19:59:31] [npo_lr2e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 19:59:37] [npo_lr2e-05] Step 5: {'step': 5, 'batch_loss': 13.044061660766602, 'forget_nll': 0.39050677967257796, 'holdout_nll': 4.704990327954293, 'retain_nll': 0.3134432365745306, 'mia_auc': 0.997925}
[2026-10-24 19:59:43] [npo_lr2e-05] Step 10: {'step': 10, 'batch_loss': 6.462507247924805, 'forget_nll': 0.8823401936702431, 'holdout_nll': 5.033795659542084, 'retain_nll': 0.5997839622199536, 'mia_auc': 0.9938}
[2026-10-24 19:59:49] [npo_lr2e-05] Step 15: {'step': 15, 'batch_loss': 0.4084354639053345, 'forget_nll': 2.4656618106365205, 'holdout_nll': 6.387885239124298, 'retain_nll': 1.842309594154358, 'mia_auc': 0.984425}
[2026-10-24 19:59:55] [npo_lr2e-05] Step 20: {'step': 20, 'batch_loss': 0.0009863435989245772, 'forget_nll': 5.546376008987426, 'holdout_nll': 9.225212426185609, 'retain_nll': 4.508338130116463, 'mia_auc': 0.940225}
[2026-10-24 19:59:58] [npo_lr2e-05] OPERATING POINT REACHED at step 20; saved to /content/drive/MyDrive/ssu_tf/ckpt/npo_lr2e-05_op
[2026-10-24 20:00:04] [npo_lr2e-05] Step 25: {'step': 25, 'batch_loss': 3.8981943362159654e-05, 'forget_nll': 8.699767785072327, 'holdout_nll': 12.29806987285614, 'retain_nll': 7.364099407196045, 'mia_auc': 0.88515}
[2026-10-24 20:00:10] [npo_lr2e-05] Step 30: {'step': 30, 'batch_loss': 4.812082954330776e-10, 'forget_nll': 11.001507222652435, 'holdout_nll': 14.553551902770996, 'retain_nll': 9.48724502325058, 'mia_auc': 0.849225}
[2026-10-24 20:00:16] [npo_lr2e-05] Step 35: {'step': 35, 'batch_loss': 1.8686935332468124e-10, 'forget_nll': 12.554836411476135, 'holdout_nll': 16.07937321662903, 'retain_nll': 10.937545020580291, 'mia_auc': 0.8278}
[2026-10-24 20:00:23] [npo_lr2e-05] Step 40: {'step': 40, 'batch_loss': 9.380191088659891e-17, 'forget_nll': 13.572874307632446, 'holdout_nll': 17.078117847442627, 'retain_nll': 11.888000197410584, 'mia_auc': 0.8135999999999999}
[2026-10-24 20:00:29] [npo_lr2e-05] Step 45: {'step': 45, 'batch_loss': 6.260105628319579e-11, 'forget_nll': 14.22096375465393, 'holdout_nll': 17.71719582557678, 'retain_nll': 12.49057255744934, 'mia_auc': 0.8061}
[2026-10-24 20:00:35] [npo_lr2e-05] Step 50: {'step': 50, 'batch_loss': 8.99244481639529e-15, 'forget_nll': 14.630574522018433, 'holdout_nll': 18.122768077850342, 'retain_nll': 12.86831767320633, 'mia_auc': 0.8013250000000001}
[2026-10-24 20:00:41] [npo_lr2e-05] Step 55: {'step': 55, 'batch_loss': 3.594802037882963e-18, 'forget_nll': 14.886137762069701, 'holdout_nll': 18.375660786628725, 'retain_nll': 13.108000640869141, 'mia_auc': 0.798675}
[2026-10-24 20:00:47] [npo_lr2e-05] Step 60: {'step': 60, 'batch_loss': 6.2312114290034165e-15, 'forget_nll': 15.044382100105286, 'holdout_nll': 18.53239068508148, 'retain_nll': 13.255521383285522, 'mia_auc': 0.7969249999999999}
[2026-10-24 20:00:53] [npo_lr2e-05] Step 65: {'step': 65, 'batch_loss': 4.509115837841632e-16, 'forget_nll': 15.142164673805237, 'holdout_nll': 18.62934564113617, 'retain_nll': 13.347565517425537, 'mia_auc': 0.795825}
[2026-10-24 20:00:59] [npo_lr2e-05] Step 70: {'step': 70, 'batch_loss': 2.15899338541054e-15, 'forget_nll': 15.202860760688782, 'holdout_nll': 18.688208770751952, 'retain_nll': 13.40391230583191, 'mia_auc': 0.79505}
[2026-10-24 20:01:05] [npo_lr2e-05] Step 75: {'step': 75, 'batch_loss': 1.0297446922935549e-10, 'forget_nll': 15.240188694000244, 'holdout_nll': 18.72493661403656, 'retain_nll': 13.438495516777039, 'mia_auc': 0.7945500000000001}
[2026-10-24 20:01:11] [npo_lr2e-05] Step 80: {'step': 80, 'batch_loss': 6.92143981018134e-11, 'forget_nll': 15.26298957824707, 'holdout_nll': 18.747430872917175, 'retain_nll': 13.459696445465088, 'mia_auc': 0.7942750000000001}
[2026-10-24 20:01:17] [npo_lr2e-05] Step 85: {'step': 85, 'batch_loss': 9.608485364821396e-22, 'forget_nll': 15.276895666122437, 'holdout_nll': 18.761163892745973, 'retain_nll': 13.472594382762908, 'mia_auc': 0.7941750000000001}
[2026-10-24 20:01:23] [npo_lr2e-05] Step 90: {'step': 90, 'batch_loss': 2.8603776790724067e-13, 'forget_nll': 15.285341658592223, 'holdout_nll': 18.769500288963318, 'retain_nll': 13.480455896854401, 'mia_auc': 0.7941}
[2026-10-24 20:01:29] [npo_lr2e-05] Step 95: {'step': 95, 'batch_loss': 4.7946577084834876e-18, 'forget_nll': 15.290467686653137, 'holdout_nll': 18.774567737579346, 'retain_nll': 13.485245962142944, 'mia_auc': 0.7941}
[2026-10-24 20:01:35] [npo_lr2e-05] Step 100: {'step': 100, 'batch_loss': 2.816140098893527e-10, 'forget_nll': 15.293588943481446, 'holdout_nll': 18.77767880439758, 'retain_nll': 13.488206038475036, 'mia_auc': 0.7941}
[2026-10-24 20:01:41] [npo_lr2e-05] Step 105: {'step': 105, 'batch_loss': 7.435863036420187e-10, 'forget_nll': 15.295427584648133, 'holdout_nll': 18.779476633071898, 'retain_nll': 13.489959790706635, 'mia_auc': 0.79405}
[2026-10-24 20:01:47] [npo_lr2e-05] Step 110: {'step': 110, 'batch_loss': 1.890329549523955e-17, 'forget_nll': 15.296488480567932, 'holdout_nll': 18.780545659065247, 'retain_nll': 13.490941710472107, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:01:53] [npo_lr2e-05] Step 115: {'step': 115, 'batch_loss': 2.701240381548786e-13, 'forget_nll': 15.297065658569336, 'holdout_nll': 18.781116943359375, 'retain_nll': 13.491500074863433, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:01:59] [npo_lr2e-05] Step 120: {'step': 120, 'batch_loss': 1.801270156256698e-18, 'forget_nll': 15.297344694137573, 'holdout_nll': 18.781416053771974, 'retain_nll': 13.491770327091217, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:05] [npo_lr2e-05] Step 125: {'step': 125, 'batch_loss': 2.1542079404261288e-16, 'forget_nll': 15.297469382286073, 'holdout_nll': 18.781546807289125, 'retain_nll': 13.491889600753785, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:11] [npo_lr2e-05] Step 130: {'step': 130, 'batch_loss': 3.537201365144682e-10, 'forget_nll': 15.297515244483948, 'holdout_nll': 18.781584515571595, 'retain_nll': 13.491947247982026, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:17] [npo_lr2e-05] Step 135: {'step': 135, 'batch_loss': 2.0206888245999366e-11, 'forget_nll': 15.297543873786926, 'holdout_nll': 18.78159903526306, 'retain_nll': 13.491954779624939, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:23] [npo_lr2e-05] Step 140: {'step': 140, 'batch_loss': 3.065243094221658e-16, 'forget_nll': 15.297550873756409, 'holdout_nll': 18.781622705459593, 'retain_nll': 13.491954028606415, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:29] [npo_lr2e-05] Step 145: {'step': 145, 'batch_loss': 1.5597506619613455e-10, 'forget_nll': 15.297559762001038, 'holdout_nll': 18.781615357398987, 'retain_nll': 13.491970436573029, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:35] [npo_lr2e-05] Step 150: {'step': 150, 'batch_loss': 3.725982956866522e-18, 'forget_nll': 15.297555017471314, 'holdout_nll': 18.781613216400146, 'retain_nll': 13.491962764263153, 'mia_auc': 0.7939749999999999}
[2026-10-24 20:02:45] [npo_lr5e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 20:02:51] [npo_lr5e-05] Step 5: {'step': 5, 'batch_loss': 8.814065933227539, 'forget_nll': 0.8980306171625853, 'holdout_nll': 5.108460586667061, 'retain_nll': 0.651064975708723, 'mia_auc': 0.9919749999999999}
[2026-10-24 20:02:57] [npo_lr5e-05] Step 10: {'step': 10, 'batch_loss': 0.0014273915439844131, 'forget_nll': 5.168179619908333, 'holdout_nll': 8.762831766605377, 'retain_nll': 4.1693700361251835, 'mia_auc': 0.9240000000000002}
[2026-10-24 20:03:04] [npo_lr5e-05] Step 15: {'step': 15, 'batch_loss': 1.3805177001557922e-09, 'forget_nll': 10.630914390087128, 'holdout_nll': 13.876150221824647, 'retain_nll': 9.133237409591676, 'mia_auc': 0.83195}
[2026-10-24 20:03:10] [npo_lr5e-05] Step 20: {'step': 20, 'batch_loss': 6.1932829876912635e-15, 'forget_nll': 14.78892352104187, 'holdout_nll': 17.81953854560852, 'retain_nll': 12.985328109264374, 'mia_auc': 0.772875}
[2026-10-24 20:03:16] [npo_lr5e-05] Step 25: {'step': 25, 'batch_loss': 2.0271513634373406e-10, 'forget_nll': 17.64284230709076, 'holdout_nll': 20.5358713722229, 'retain_nll': 15.648374247550965, 'mia_auc': 0.741275}
[2026-10-24 20:03:22] [npo_lr5e-05] Step 30: {'step': 30, 'batch_loss': 7.479807158790354e-18, 'forget_nll': 19.527134523391723, 'holdout_nll': 22.333513412475586, 'retain_nll': 17.40469973087311, 'mia_auc': 0.723875}
[2026-10-24 20:03:28] [npo_lr5e-05] Step 35: {'step': 35, 'batch_loss': 3.507181697837147e-11, 'forget_nll': 20.73538906097412, 'holdout_nll': 23.488894901275636, 'retain_nll': 18.53099208831787, 'mia_auc': 0.7137499999999999}
[2026-10-24 20:03:34] [npo_lr5e-05] Step 40: {'step': 40, 'batch_loss': 1.1561384877947718e-21, 'forget_nll': 21.495464386940004, 'holdout_nll': 24.216394901275635, 'retain_nll': 19.248876390457152, 'mia_auc': 0.70865}
[2026-10-24 20:03:40] [npo_lr5e-05] Step 45: {'step': 45, 'batch_loss': 1.167589245773537e-13, 'forget_nll': 21.97209776878357, 'holdout_nll': 24.675483045578, 'retain_nll': 19.703387913703917, 'mia_auc': 0.705225}
[2026-10-24 20:03:46] [npo_lr5e-05] Step 50: {'step': 50, 'batch_loss': 2.0142020005672698e-25, 'forget_nll': 22.271340408325194, 'holdout_nll': 24.961530256271363, 'retain_nll': 19.987881655693055, 'mia_auc': 0.703225}
[2026-10-24 20:03:52] [npo_lr5e-05] Step 55: {'step': 55, 'batch_loss': 8.225757159048905e-24, 'forget_nll': 22.455648880004883, 'holdout_nll': 25.139159154891967, 'retain_nll': 20.164239392280578, 'mia_auc': 0.7021249999999999}
[2026-10-24 20:03:58] [npo_lr5e-05] Step 60: {'step': 60, 'batch_loss': 9.71368028207698e-22, 'forget_nll': 22.570195593833922, 'holdout_nll': 25.24907636642456, 'retain_nll': 20.274368672370912, 'mia_auc': 0.7011999999999999}
[2026-10-24 20:04:04] [npo_lr5e-05] Step 65: {'step': 65, 'batch_loss': 7.6203184444205835e-25, 'forget_nll': 22.640923185348512, 'holdout_nll': 25.316717586517335, 'retain_nll': 20.34151773452759, 'mia_auc': 0.7009}
[2026-10-24 20:04:10] [npo_lr5e-05] Step 70: {'step': 70, 'batch_loss': 4.5484052711069755e-21, 'forget_nll': 22.684277124404908, 'holdout_nll': 25.35814956665039, 'retain_nll': 20.382783513069153, 'mia_auc': 0.700425}
[2026-10-24 20:04:16] [npo_lr5e-05] Step 75: {'step': 75, 'batch_loss': 4.706252780516883e-18, 'forget_nll': 22.711104230880736, 'holdout_nll': 25.383402709960937, 'retain_nll': 20.408079075813294, 'mia_auc': 0.7003}
[2026-10-24 20:04:22] [npo_lr5e-05] Step 80: {'step': 80, 'batch_loss': 1.0983574482868394e-14, 'forget_nll': 22.72741479873657, 'holdout_nll': 25.398739595413208, 'retain_nll': 20.42351728439331, 'mia_auc': 0.70025}
[2026-10-24 20:04:28] [npo_lr5e-05] Step 85: {'step': 85, 'batch_loss': 6.995933470020529e-32, 'forget_nll': 22.737324242591857, 'holdout_nll': 25.40810185432434, 'retain_nll': 20.43293637752533, 'mia_auc': 0.700225}
[2026-10-24 20:04:34] [npo_lr5e-05] Step 90: {'step': 90, 'batch_loss': 2.893230597879005e-20, 'forget_nll': 22.74340284347534, 'holdout_nll': 25.41383613586426, 'retain_nll': 20.438667616844178, 'mia_auc': 0.700175}
[2026-10-24 20:04:40] [npo_lr5e-05] Step 95: {'step': 95, 'batch_loss': 1.3003966863607458e-21, 'forget_nll': 22.747103366851807, 'holdout_nll': 25.417333478927613, 'retain_nll': 20.442168221473693, 'mia_auc': 0.70015}
[2026-10-24 20:04:46] [npo_lr5e-05] Step 100: {'step': 100, 'batch_loss': 2.941654793288829e-15, 'forget_nll': 22.749345064163208, 'holdout_nll': 25.419452600479126, 'retain_nll': 20.444298133850097, 'mia_auc': 0.700125}
[2026-10-24 20:04:52] [npo_lr5e-05] Step 105: {'step': 105, 'batch_loss': 1.6067797283204738e-18, 'forget_nll': 22.75065591812134, 'holdout_nll': 25.420716791152955, 'retain_nll': 20.445554490089417, 'mia_auc': 0.700125}
[2026-10-24 20:04:58] [npo_lr5e-05] Step 110: {'step': 110, 'batch_loss': 3.859337971456161e-21, 'forget_nll': 22.75141311645508, 'holdout_nll': 25.421428670883177, 'retain_nll': 20.446274886131288, 'mia_auc': 0.7001}
[2026-10-24 20:05:04] [npo_lr5e-05] Step 115: {'step': 115, 'batch_loss': 3.3193672307199025e-19, 'forget_nll': 22.75182514667511, 'holdout_nll': 25.421820669174195, 'retain_nll': 20.446659874916076, 'mia_auc': 0.7001}
[2026-10-24 20:05:10] [npo_lr5e-05] Step 120: {'step': 120, 'batch_loss': 3.44107122200285e-23, 'forget_nll': 22.75201714515686, 'holdout_nll': 25.421993188858032, 'retain_nll': 20.44683771133423, 'mia_auc': 0.7001}
[2026-10-24 20:05:16] [npo_lr5e-05] Step 125: {'step': 125, 'batch_loss': 1.4811026316415334e-21, 'forget_nll': 22.752111167907714, 'holdout_nll': 25.422087659835814, 'retain_nll': 20.446925382614136, 'mia_auc': 0.7001}
[2026-10-24 20:05:22] [npo_lr5e-05] Step 130: {'step': 130, 'batch_loss': 3.198927667896756e-12, 'forget_nll': 22.752148351669312, 'holdout_nll': 25.422118148803712, 'retain_nll': 20.446962890625, 'mia_auc': 0.7001}
[2026-10-24 20:05:28] [npo_lr5e-05] Step 135: {'step': 135, 'batch_loss': 6.448361904028992e-17, 'forget_nll': 22.752154221534727, 'holdout_nll': 25.422142524719238, 'retain_nll': 20.446982712745665, 'mia_auc': 0.7001}
[2026-10-24 20:05:34] [npo_lr5e-05] Step 140: {'step': 140, 'batch_loss': 1.200583441309452e-22, 'forget_nll': 22.752161436080932, 'holdout_nll': 25.42213812828064, 'retain_nll': 20.446980361938476, 'mia_auc': 0.7001}
[2026-10-24 20:05:40] [npo_lr5e-05] Step 145: {'step': 145, 'batch_loss': 1.0594269669980845e-14, 'forget_nll': 22.752167840003967, 'holdout_nll': 25.422144527435304, 'retain_nll': 20.44698508262634, 'mia_auc': 0.7001}
[2026-10-24 20:05:46] [npo_lr5e-05] Step 150: {'step': 150, 'batch_loss': 3.6781674691437325e-23, 'forget_nll': 22.75217055797577, 'holdout_nll': 25.422147846221925, 'retain_nll': 20.446987733840942, 'mia_auc': 0.7001}
[2026-10-24 20:05:52] [retainft_lr2e-05] Step 0: {'step': 0, 'batch_loss': None, 'forget_nll': 0.26313516072579657, 'holdout_nll': 4.692464680671692, 'retain_nll': 0.28390602122060954, 'mia_auc': 0.998775}
[2026-10-24 20:05:58] [retainft_lr2e-05] Step 5: {'step': 5, 'batch_loss': 0.25754979252815247, 'forget_nll': 0.28006695495918393, 'holdout_nll': 4.749055930227041, 'retain_nll': 0.3012852547643706, 'mia_auc': 0.99925}
[2026-10-24 20:06:03] [retainft_lr2e-05] Step 10: {'step': 10, 'batch_loss': 0.4240572452545166, 'forget_nll': 0.3181423945422284, 'holdout_nll': 4.855783537626267, 'retain_nll': 0.34058038050308825, 'mia_auc': 0.998725}
[2026-10-24 20:06:09] [retainft_lr2e-05] Step 15: {'step': 15, 'batch_loss': 0.23641104996204376, 'forget_nll': 0.34071925153024496, 'holdout_nll': 4.898967234790325, 'retain_nll': 0.3595958449179307, 'mia_auc': 0.998175}
[2026-10-24 20:06:15] [retainft_lr2e-05] Step 20: {'step': 20, 'batch_loss': 0.5992343425750732, 'forget_nll': 0.3529336756491102, 'holdout_nll': 4.901838529109955, 'retain_nll': 0.3701963330199942, 'mia_auc': 0.9970749999999999}
[2026-10-24 20:06:20] [retainft_lr2e-05] Step 25: {'step': 25, 'batch_loss': 0.296375036239624, 'forget_nll': 0.36364936047117224, 'holdout_nll': 4.897788188159466, 'retain_nll': 0.3799412987101823, 'mia_auc': 0.9966499999999999}
[2026-10-24 20:06:26] [retainft_lr2e-05] Step 30: {'step': 30, 'batch_loss': 0.3544309735298157, 'forget_nll': 0.3695126667059958, 'holdout_nll': 4.869264206290245, 'retain_nll': 0.3824974391050637, 'mia_auc': 0.996925}
[2026-10-24 20:06:32] [retainft_lr2e-05] Step 35: {'step': 35, 'batch_loss': 0.3405013978481293, 'forget_nll': 0.3737561144120991, 'holdout_nll': 4.831555696725846, 'retain_nll': 0.38259554161690174, 'mia_auc': 0.997525}
[2026-10-24 20:06:37] [retainft_lr2e-05] Step 40: {'step': 40, 'batch_loss': 0.4502425491809845, 'forget_nll': 0.3809541274397634, 'holdout_nll': 4.8138430726528165, 'retain_nll': 0.38226056662388147, 'mia_auc': 0.997425}
[2026-10-24 20:06:43] [retainft_lr2e-05] Step 45: {'step': 45, 'batch_loss': 0.4668066203594208, 'forget_nll': 0.38545391719788313, 'holdout_nll': 4.82935169249773, 'retain_nll': 0.3782159838359803, 'mia_auc': 0.99905}
[2026-10-24 20:06:49] [retainft_lr2e-05] Step 50: {'step': 50, 'batch_loss': 0.3316234052181244, 'forget_nll': 0.3842939511639997, 'holdout_nll': 4.827107235789299, 'retain_nll': 0.37480106519535183, 'mia_auc': 0.99895}
[2026-10-24 20:06:55] [retainft_lr2e-05] Step 55: {'step': 55, 'batch_loss': 0.4793682396411896, 'forget_nll': 0.38625850847922266, 'holdout_nll': 4.827469522058964, 'retain_nll': 0.3685254850424826, 'mia_auc': 0.998725}
[2026-10-24 20:07:00] [retainft_lr2e-05] Step 60: {'step': 60, 'batch_loss': 0.3769746422767639, 'forget_nll': 0.39276730226352813, 'holdout_nll': 4.8268875375390055, 'retain_nll': 0.37155810862313954, 'mia_auc': 0.998675}
[2026-10-24 20:07:06] [retainft_lr2e-05] Step 65: {'step': 65, 'batch_loss': 0.32090887427330017, 'forget_nll': 0.4058991097426042, 'holdout_nll': 4.846962341964245, 'retain_nll': 0.37890314077958465, 'mia_auc': 0.99815}
[2026-10-24 20:07:12] [retainft_lr2e-05] Step 70: {'step': 70, 'batch_loss': 0.46058931946754456, 'forget_nll': 0.4113022488192655, 'holdout_nll': 4.861453628093004, 'retain_nll': 0.37570517636369916, 'mia_auc': 0.996975}
[2026-10-24 20:07:17] [retainft_lr2e-05] Step 75: {'step': 75, 'batch_loss': 0.34238576889038086, 'forget_nll': 0.4158912321808748, 'holdout_nll': 4.8652378693223, 'retain_nll': 0.37541672389023006, 'mia_auc': 0.99585}
[2026-10-24 20:07:23] [retainft_lr2e-05] Step 80: {'step': 80, 'batch_loss': 0.3632076680660248, 'forget_nll': 0.41375853834673765, 'holdout_nll': 4.884389925301075, 'retain_nll': 0.3764822960738093, 'mia_auc': 0.996475}
[2026-10-24 20:07:29] [retainft_lr2e-05] Step 85: {'step': 85, 'batch_loss': 0.3550877571105957, 'forget_nll': 0.4110750269982964, 'holdout_nll': 4.8946150176227095, 'retain_nll': 0.3754718158673495, 'mia_auc': 0.99785}
[2026-10-24 20:07:34] [retainft_lr2e-05] Step 90: {'step': 90, 'batch_loss': 0.49739745259284973, 'forget_nll': 0.41804296310525385, 'holdout_nll': 4.90763030141592, 'retain_nll': 0.38026305752806366, 'mia_auc': 0.99815}
[2026-10-24 20:07:40] [retainft_lr2e-05] Step 95: {'step': 95, 'batch_loss': 0.4794538617134094, 'forget_nll': 0.42269802835653536, 'holdout_nll': 4.892458540201187, 'retain_nll': 0.37724778541363774, 'mia_auc': 0.99805}
[2026-10-24 20:07:45] [retainft_lr2e-05] Step 100: {'step': 100, 'batch_loss': 0.34599924087524414, 'forget_nll': 0.42510190691798927, 'holdout_nll': 4.873843987882137, 'retain_nll': 0.37037566740065814, 'mia_auc': 0.9984}
[2026-10-24 20:07:51] [retainft_lr2e-05] Step 105: {'step': 105, 'batch_loss': 0.5615683197975159, 'forget_nll': 0.436922136512585, 'holdout_nll': 4.865006082355976, 'retain_nll': 0.3760684025567025, 'mia_auc': 0.9983}
[2026-10-24 20:07:57] [retainft_lr2e-05] Step 110: {'step': 110, 'batch_loss': 0.5666208863258362, 'forget_nll': 0.4345532387774438, 'holdout_nll': 4.870564559400082, 'retain_nll': 0.3728342472575605, 'mia_auc': 0.99795}
[2026-10-24 20:08:03] [retainft_lr2e-05] Step 115: {'step': 115, 'batch_loss': 0.47863316535949707, 'forget_nll': 0.42879273364320397, 'holdout_nll': 4.899186738431454, 'retain_nll': 0.3707938902173191, 'mia_auc': 0.9982}
[2026-10-24 20:08:08] [retainft_lr2e-05] Step 120: {'step': 120, 'batch_loss': 0.5053746104240417, 'forget_nll': 0.42397220673039554, 'holdout_nll': 4.915624218285084, 'retain_nll': 0.36763408209197224, 'mia_auc': 0.998975}
[2026-10-24 20:08:14] [retainft_lr2e-05] Step 125: {'step': 125, 'batch_loss': 0.40609392523765564, 'forget_nll': 0.42280494085745884, 'holdout_nll': 4.9136483857035635, 'retain_nll': 0.3731715177372098, 'mia_auc': 0.9990249999999999}
[2026-10-24 20:08:20] [retainft_lr2e-05] Step 130: {'step': 130, 'batch_loss': 0.36388859152793884, 'forget_nll': 0.43050483191385863, 'holdout_nll': 4.89462422221899, 'retain_nll': 0.3784912069514394, 'mia_auc': 0.998875}
[2026-10-24 20:08:25] [retainft_lr2e-05] Step 135: {'step': 135, 'batch_loss': 0.38655975461006165, 'forget_nll': 0.43658052765764294, 'holdout_nll': 4.865093582868576, 'retain_nll': 0.38297026239335535, 'mia_auc': 0.998275}
[2026-10-24 20:08:31] [retainft_lr2e-05] Step 140: {'step': 140, 'batch_loss': 0.5580136179924011, 'forget_nll': 0.44327121069654823, 'holdout_nll': 4.856977244913578, 'retain_nll': 0.3822710602427833, 'mia_auc': 0.997775}
[2026-10-24 20:08:37] [retainft_lr2e-05] Step 145: {'step': 145, 'batch_loss': 0.6304628849029541, 'forget_nll': 0.4509650661842898, 'holdout_nll': 4.879938661754132, 'retain_nll': 0.3792186765372753, 'mia_auc': 0.997225}
[2026-10-24 20:08:42] [retainft_lr2e-05] Step 150: {'step': 150, 'batch_loss': 0.383169949054718, 'forget_nll': 0.4539131297566928, 'holdout_nll': 4.891823060512543, 'retain_nll': 0.3803681288519874, 'mia_auc': 0.996925}
[2026-10-24 20:08:48] STAGE 5: Full evaluation battery
[2026-10-24 20:09:05] [eval pretrained] {"name": "pretrained", "forget_nll": 2.809641990959644, "holdout_nll": 2.7942432737350464, "retain_nll": 2.8124940201640127, "mia_auc": 0.493375, "mink_auc": 0.5011000000000001, "real_authors_nll": 3.8726323330402375, "world_facts_nll": 4.913581950032813, "forget_rouge": 0.23697529606527368, "retain_rouge": 0.19836051466991386, "ks_stat": 0.565, "ks_p": 8.970241343959439e-30, "ckpt": "EleutherAI/pythia-160m", "seconds": 15.474528789520264}
[2026-10-24 20:09:17] [eval target] {"name": "target", "forget_nll": 0.26313516072579657, "holdout_nll": 4.692464680671692, "retain_nll": 0.28390602122060954, "mia_auc": 0.998775, "mink_auc": 0.999, "real_authors_nll": 14.890170164108277, "world_facts_nll": 16.767929399115406, "forget_rouge": 0.6538872918956059, "retain_rouge": 0.5381845233032816, "ks_stat": 0.99, "ks_p": 1.550229472718744e-114, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/target_final", "seconds": 11.763395309448242}
[2026-10-24 20:09:30] [eval oracle] {"name": "oracle", "forget_nll": 4.279312668740749, "holdout_nll": 4.506351673305034, "retain_nll": 0.3348911778070033, "mia_auc": 0.55115, "mink_auc": 0.564125, "real_authors_nll": 15.812378067970275, "world_facts_nll": 17.181695534632755, "forget_rouge": 0.2694049501945276, "retain_rouge": 0.49087731406580654, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/oracle_final", "seconds": 11.875998258590698}
[2026-10-24 20:09:43] [eval ga_lr2e-05] {"name": "ga_lr2e-05", "forget_nll": 7.317203567028046, "holdout_nll": 11.248352377414703, "retain_nll": 6.027548713088035, "mia_auc": 0.891575, "mink_auc": 0.818425, "real_authors_nll": 22.360138216018676, "world_facts_nll": 27.5695859305879, "forget_rouge": 0.11461352030227809, "retain_rouge": 0.13423274503056595, "ks_stat": 0.61, "ks_p": 5.022256080866513e-35, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/ga_lr2e-05_op", "seconds": 13.518894910812378}
[2026-10-24 20:09:57] [eval graddiff_lr2e-05] {"name": "graddiff_lr2e-05", "forget_nll": 5.185332969427109, "holdout_nll": 7.561460986733437, "retain_nll": 2.086949961073697, "mia_auc": 0.7757499999999999, "mink_auc": 0.68285, "real_authors_nll": 15.463373656272887, "world_facts_nll": 18.991419531341293, "forget_rouge": 0.2072300885742736, "retain_rouge": 0.19952823405161269, "ks_stat": 0.245, "ks_p": 1.1150402145378719e-05, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/graddiff_lr2e-05_op", "seconds": 12.771035432815552}
[2026-10-24 20:10:10] [eval npo_lr2e-05] {"name": "npo_lr2e-05", "forget_nll": 5.546376008987426, "holdout_nll": 9.225212426185609, "retain_nll": 4.508338130116463, "mia_auc": 0.940225, "mink_auc": 0.8613500000000001, "real_authors_nll": 21.429184913635254, "world_facts_nll": 25.88892853565705, "forget_rouge": 0.14480843303017127, "retain_rouge": 0.15159102359886684, "ks_stat": 0.395, "ks_p": 2.5656301025789152e-14, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/npo_lr2e-05_op", "seconds": 13.342858791351318}
[2026-10-24 20:10:24] [eval retainft_lr2e-05] {"name": "retainft_lr2e-05", "forget_nll": 0.4539131297566928, "holdout_nll": 4.891823060512543, "retain_nll": 0.3803681288519874, "mia_auc": 0.996925, "mink_auc": 0.996625, "real_authors_nll": 14.505437021255494, "world_facts_nll": 16.61879404182108, "forget_rouge": 0.4684120319501772, "retain_rouge": 0.5039440692272135, "ks_stat": 0.98, "ks_p": 2.0412129838866487e-110, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/retainft_lr2e-05_final", "seconds": 13.348013162612915}
[2026-10-24 20:10:24] STAGE 6: Relearning probe
[2026-10-24 20:10:36] [relearn oracle] {'pre_nll': 4.344039522608122, 'post_nll': 3.6872576723496118, 'post_rouge': 0.3071647212754054, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-24 20:10:46] [relearn ga_lr2e-05] {'pre_nll': 7.400629148218367, 'post_nll': 1.079155547502968, 'post_rouge': 0.32914181547603627, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-24 20:10:57] [relearn graddiff_lr2e-05] {'pre_nll': 5.233722532457776, 'post_nll': 1.9013308151314656, 'post_rouge': 0.30347687603750334, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-24 20:11:08] [relearn npo_lr2e-05] {'pre_nll': 5.5990899483362835, 'post_nll': 1.0197747631826335, 'post_rouge': 0.3226331336930621, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-24 20:11:18] [relearn retainft_lr2e-05] {'pre_nll': 0.4591822882105286, 'post_nll': 0.5724854730431819, 'post_rouge': 0.44934080095176865, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-24 20:11:19] STAGE 7: Compiling report and generating plots from JSON
[2026-10-24 20:11:20] Report written: /content/drive/MyDrive/ssu_tf/report.md
[2026-10-24 20:11:20] STAGE 8 (OPTIONAL): Mamba-130M feasibility benchmark
[2026-10-25 06:22:07] STAGE 0: environment + benchmark
[2026-10-25 06:22:08] disk free where results are stored: 197.0 GB
[2026-10-25 06:22:35] bench fp32 bs8: {'s_per_step': 0.25466203689575195, 'peak_mem_gb': 3.513216, 'finite': True, 'proj_epoch_min': 2.016074458758036}
[2026-10-25 06:22:38] bench fp32 bs16: {'s_per_step': 0.36571612358093264, 'peak_mem_gb': 4.403297792, 'finite': True, 'proj_epoch_min': 1.4506739568710327}
[2026-10-25 06:22:40] GATE G0: PASS | {"proj_epoch_min": 1.4506739568710327, "use_fp16_ft": false, "limit_min": 8.0, "finite": true}
[2026-10-25 06:22:40] STAGE 1: data
[2026-10-25 06:22:40] G1 already passed, skipping
[2026-10-25 06:22:41] STAGE 1b: perturbed splits for TOFU-style metrics
[2026-10-25 06:22:44]   forget05_perturbed: columns=['question', 'answer', 'paraphrased_answer', 'perturbed_answer', 'paraphrased_question'] raw=200 used=200
[2026-10-25 06:22:45]   retain_perturbed: columns=['question', 'answer', 'paraphrased_answer', 'perturbed_answer', 'paraphrased_question'] raw=400 used=200
[2026-10-25 06:22:46]   real_authors_perturbed: columns=['question', 'answer', 'perturbed_answer'] raw=100 used=0
[2026-10-25 06:22:47]   world_facts_perturbed: columns=['question', 'answer', 'perturbed_answer'] raw=117 used=0
[2026-10-25 06:22:47]   Model Utility possible: False | Forget Quality possible: True
[2026-10-25 06:22:48] STAGE 2: target model
[2026-10-25 06:22:48] G2 already passed, skipping
[2026-10-25 06:22:48] STAGE 3: oracle
[2026-10-25 06:22:49] G3 already passed, skipping
[2026-10-25 06:22:49] STAGE 4: unlearning sweep
[2026-10-25 06:23:35] [ga_lr3e-06] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:23:38] [ga_lr3e-06] step 3: forget 0.269 retain +-0.000 mia 1.000
[2026-10-25 06:23:42] [ga_lr3e-06] step 6: forget 0.281 retain +0.001 mia 1.000
[2026-10-25 06:23:45] [ga_lr3e-06] step 9: forget 0.294 retain +0.002 mia 1.000
[2026-10-25 06:23:48] [ga_lr3e-06] step 12: forget 0.308 retain +0.004 mia 1.000
[2026-10-25 06:23:52] [ga_lr3e-06] step 15: forget 0.323 retain +0.005 mia 1.000
[2026-10-25 06:23:55] [ga_lr3e-06] step 18: forget 0.338 retain +0.008 mia 1.000
[2026-10-25 06:23:58] [ga_lr3e-06] step 21: forget 0.354 retain +0.010 mia 1.000
[2026-10-25 06:24:01] [ga_lr3e-06] step 24: forget 0.372 retain +0.013 mia 1.000
[2026-10-25 06:24:05] [ga_lr3e-06] step 27: forget 0.390 retain +0.017 mia 1.000
[2026-10-25 06:24:08] [ga_lr3e-06] step 30: forget 0.411 retain +0.021 mia 0.999
[2026-10-25 06:24:11] [ga_lr3e-06] step 33: forget 0.434 retain +0.027 mia 0.999
[2026-10-25 06:24:15] [ga_lr3e-06] step 36: forget 0.461 retain +0.033 mia 0.999
[2026-10-25 06:24:18] [ga_lr3e-06] step 39: forget 0.491 retain +0.042 mia 0.999
[2026-10-25 06:24:21] [ga_lr3e-06] step 42: forget 0.525 retain +0.055 mia 0.999
[2026-10-25 06:24:25] [ga_lr3e-06] step 45: forget 0.569 retain +0.075 mia 0.998
[2026-10-25 06:24:28] [ga_lr3e-06] step 48: forget 0.622 retain +0.103 mia 0.998
[2026-10-25 06:24:32] [ga_lr3e-06] step 51: forget 0.687 retain +0.142 mia 0.998
[2026-10-25 06:24:35] [ga_lr3e-06] step 54: forget 0.762 retain +0.193 mia 0.997
[2026-10-25 06:24:39] [ga_lr3e-06] step 57: forget 0.859 retain +0.263 mia 0.997
[2026-10-25 06:24:42] [ga_lr3e-06] step 60: forget 0.979 retain +0.354 mia 0.997
[2026-10-25 06:24:46] [ga_lr3e-06] step 63: forget 1.124 retain +0.468 mia 0.996
[2026-10-25 06:24:50] [ga_lr3e-06] step 66: forget 1.299 retain +0.607 mia 0.996
[2026-10-25 06:24:53] [ga_lr3e-06] step 69: forget 1.501 retain +0.767 mia 0.995
[2026-10-25 06:24:57] [ga_lr3e-06] step 72: forget 1.733 retain +0.951 mia 0.993
[2026-10-25 06:25:00] [ga_lr3e-06] step 75: forget 1.998 retain +1.163 mia 0.991
[2026-10-25 06:25:04] [ga_lr3e-06] step 78: forget 2.282 retain +1.392 mia 0.988
[2026-10-25 06:25:08] [ga_lr3e-06] step 81: forget 2.588 retain +1.639 mia 0.984
[2026-10-25 06:25:11] [ga_lr3e-06] step 84: forget 2.928 retain +1.916 mia 0.980
[2026-10-25 06:25:15] [ga_lr3e-06] step 87: forget 3.311 retain +2.226 mia 0.974
[2026-10-25 06:25:19] [ga_lr3e-06] step 90: forget 3.756 retain +2.591 mia 0.965
[2026-10-25 06:25:23] [ga_lr3e-06] step 93: forget 4.269 retain +3.017 mia 0.955
[2026-10-25 06:25:27] [ga_lr3e-06] step 96: forget 4.862 retain +3.512 mia 0.946
[2026-10-25 06:25:32] [ga_lr3e-06] OPERATING POINT at step 96 (forget NLL reached the oracle's)
[2026-10-25 06:25:35] [ga_lr3e-06] step 99: forget 5.489 retain +4.040 mia 0.931
[2026-10-25 06:25:39] [ga_lr3e-06] step 102: forget 6.189 retain +4.638 mia 0.915
[2026-10-25 06:25:43] [ga_lr3e-06] step 105: forget 7.042 retain +5.375 mia 0.891
[2026-10-25 06:25:44] [ga_lr3e-06] finished: reached, op_step=96, promoted=True, 131s
[2026-10-25 06:25:48] [ga_lr1e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:25:52] [ga_lr1e-05] step 3: forget 0.280 retain +0.001 mia 1.000
[2026-10-25 06:25:56] [ga_lr1e-05] step 6: forget 0.327 retain +0.011 mia 1.000
[2026-10-25 06:26:00] [ga_lr1e-05] step 9: forget 0.389 retain +0.027 mia 0.999
[2026-10-25 06:26:04] [ga_lr1e-05] step 12: forget 0.463 retain +0.055 mia 0.999
[2026-10-25 06:26:08] [ga_lr1e-05] step 15: forget 0.571 retain +0.107 mia 0.998
[2026-10-25 06:26:12] [ga_lr1e-05] step 18: forget 0.764 retain +0.231 mia 0.997
[2026-10-25 06:26:16] [ga_lr1e-05] step 21: forget 1.101 retain +0.487 mia 0.996
[2026-10-25 06:26:20] [ga_lr1e-05] step 24: forget 1.601 retain +0.895 mia 0.993
[2026-10-25 06:26:24] [ga_lr1e-05] step 27: forget 2.314 retain +1.484 mia 0.984
[2026-10-25 06:26:28] [ga_lr1e-05] step 30: forget 3.284 retain +2.303 mia 0.967
[2026-10-25 06:26:32] [ga_lr1e-05] step 33: forget 4.700 retain +3.519 mia 0.939
[2026-10-25 06:26:36] [ga_lr1e-05] OPERATING POINT at step 33 (forget NLL reached the oracle's)
[2026-10-25 06:26:40] [ga_lr1e-05] step 36: forget 6.824 retain +5.424 mia 0.903
[2026-10-25 06:26:44] [ga_lr1e-05] step 39: forget 10.055 retain +8.416 mia 0.863
[2026-10-25 06:26:48] [ga_lr1e-05] step 42: forget 14.939 retain +12.999 mia 0.820
[2026-10-25 06:26:48] [ga_lr1e-05] finished: reached, op_step=33, promoted=False, 63s
[2026-10-25 06:26:53] [ga_lr3e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:26:56] [ga_lr3e-05] step 3: forget 0.331 retain +0.014 mia 1.000
[2026-10-25 06:27:00] [ga_lr3e-05] step 6: forget 0.621 retain +0.156 mia 0.996
[2026-10-25 06:27:04] [ga_lr3e-05] step 9: forget 1.465 retain +0.772 mia 0.987
[2026-10-25 06:27:08] [ga_lr3e-05] step 12: forget 3.418 retain +2.346 mia 0.952
[2026-10-25 06:27:12] [ga_lr3e-05] step 15: forget 7.845 retain +6.248 mia 0.856
[2026-10-25 06:27:16] [ga_lr3e-05] OPERATING POINT at step 15 (forget NLL reached the oracle's)
[2026-10-25 06:27:20] [ga_lr3e-05] step 18: forget 18.360 retain +15.905 mia 0.742
[2026-10-25 06:27:20] [ga_lr3e-05] DIVERGED at step 21 (loss -31.857877731323242, forget batch NLL 31.857877731323242)
[2026-10-25 06:27:20] [ga_lr3e-05] finished: reached, op_step=15, promoted=False, 31s
[2026-10-25 06:27:24] [graddiff_lr3e-06] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:27:29] [graddiff_lr3e-06] step 3: forget 0.266 retain +-0.001 mia 1.000
[2026-10-25 06:27:33] [graddiff_lr3e-06] step 6: forget 0.274 retain +-0.000 mia 1.000
[2026-10-25 06:27:38] [graddiff_lr3e-06] step 9: forget 0.283 retain +0.000 mia 1.000
[2026-10-25 06:27:43] [graddiff_lr3e-06] step 12: forget 0.293 retain +0.002 mia 1.000
[2026-10-25 06:27:47] [graddiff_lr3e-06] step 15: forget 0.303 retain +0.003 mia 1.000
[2026-10-25 06:27:52] [graddiff_lr3e-06] step 18: forget 0.314 retain +0.004 mia 1.000
[2026-10-25 06:27:56] [graddiff_lr3e-06] step 21: forget 0.325 retain +0.005 mia 1.000
[2026-10-25 06:28:01] [graddiff_lr3e-06] step 24: forget 0.336 retain +0.006 mia 1.000
[2026-10-25 06:28:05] [graddiff_lr3e-06] step 27: forget 0.346 retain +0.007 mia 1.000
[2026-10-25 06:28:09] [graddiff_lr3e-06] step 30: forget 0.358 retain +0.008 mia 1.000
[2026-10-25 06:28:14] [graddiff_lr3e-06] step 33: forget 0.370 retain +0.008 mia 1.000
[2026-10-25 06:28:18] [graddiff_lr3e-06] step 36: forget 0.384 retain +0.009 mia 0.999
[2026-10-25 06:28:23] [graddiff_lr3e-06] step 39: forget 0.397 retain +0.009 mia 0.999
[2026-10-25 06:28:27] [graddiff_lr3e-06] step 42: forget 0.408 retain +0.010 mia 0.999
[2026-10-25 06:28:32] [graddiff_lr3e-06] step 45: forget 0.423 retain +0.011 mia 0.999
[2026-10-25 06:28:36] [graddiff_lr3e-06] step 48: forget 0.437 retain +0.013 mia 0.999
[2026-10-25 06:28:41] [graddiff_lr3e-06] step 51: forget 0.452 retain +0.013 mia 0.999
[2026-10-25 06:28:45] [graddiff_lr3e-06] step 54: forget 0.468 retain +0.014 mia 0.999
[2026-10-25 06:28:50] [graddiff_lr3e-06] step 57: forget 0.484 retain +0.014 mia 0.999
[2026-10-25 06:28:54] [graddiff_lr3e-06] step 60: forget 0.502 retain +0.015 mia 0.998
[2026-10-25 06:28:58] [graddiff_lr3e-06] step 63: forget 0.521 retain +0.016 mia 0.998
[2026-10-25 06:29:03] [graddiff_lr3e-06] step 66: forget 0.542 retain +0.018 mia 0.998
[2026-10-25 06:29:07] [graddiff_lr3e-06] step 69: forget 0.565 retain +0.021 mia 0.998
[2026-10-25 06:29:12] [graddiff_lr3e-06] step 72: forget 0.588 retain +0.023 mia 0.997
[2026-10-25 06:29:16] [graddiff_lr3e-06] step 75: forget 0.610 retain +0.026 mia 0.997
[2026-10-25 06:29:21] [graddiff_lr3e-06] step 78: forget 0.632 retain +0.029 mia 0.997
[2026-10-25 06:29:25] [graddiff_lr3e-06] step 81: forget 0.657 retain +0.033 mia 0.997
[2026-10-25 06:29:30] [graddiff_lr3e-06] step 84: forget 0.682 retain +0.038 mia 0.996
[2026-10-25 06:29:34] [graddiff_lr3e-06] step 87: forget 0.710 retain +0.043 mia 0.996
[2026-10-25 06:29:39] [graddiff_lr3e-06] step 90: forget 0.741 retain +0.048 mia 0.996
[2026-10-25 06:29:43] [graddiff_lr3e-06] step 93: forget 0.773 retain +0.053 mia 0.996
[2026-10-25 06:29:48] [graddiff_lr3e-06] step 96: forget 0.810 retain +0.059 mia 0.995
[2026-10-25 06:29:52] [graddiff_lr3e-06] step 99: forget 0.844 retain +0.065 mia 0.995
[2026-10-25 06:29:57] [graddiff_lr3e-06] step 102: forget 0.878 retain +0.071 mia 0.995
[2026-10-25 06:30:01] [graddiff_lr3e-06] step 105: forget 0.913 retain +0.078 mia 0.994
[2026-10-25 06:30:06] [graddiff_lr3e-06] step 108: forget 0.952 retain +0.086 mia 0.994
[2026-10-25 06:30:10] [graddiff_lr3e-06] step 111: forget 0.993 retain +0.094 mia 0.994
[2026-10-25 06:30:15] [graddiff_lr3e-06] step 114: forget 1.037 retain +0.103 mia 0.993
[2026-10-25 06:30:19] [graddiff_lr3e-06] step 117: forget 1.080 retain +0.112 mia 0.993
[2026-10-25 06:30:24] [graddiff_lr3e-06] step 120: forget 1.120 retain +0.121 mia 0.992
[2026-10-25 06:30:28] [graddiff_lr3e-06] step 123: forget 1.159 retain +0.129 mia 0.991
[2026-10-25 06:30:32] [graddiff_lr3e-06] step 126: forget 1.199 retain +0.137 mia 0.990
[2026-10-25 06:30:37] [graddiff_lr3e-06] step 129: forget 1.241 retain +0.147 mia 0.990
[2026-10-25 06:30:41] [graddiff_lr3e-06] step 132: forget 1.286 retain +0.157 mia 0.988
[2026-10-25 06:30:46] [graddiff_lr3e-06] step 135: forget 1.339 retain +0.169 mia 0.987
[2026-10-25 06:30:50] [graddiff_lr3e-06] step 138: forget 1.393 retain +0.183 mia 0.985
[2026-10-25 06:30:55] [graddiff_lr3e-06] step 141: forget 1.450 retain +0.197 mia 0.984
[2026-10-25 06:30:59] [graddiff_lr3e-06] step 144: forget 1.508 retain +0.210 mia 0.982
[2026-10-25 06:31:03] [graddiff_lr3e-06] step 147: forget 1.574 retain +0.225 mia 0.981
[2026-10-25 06:31:08] [graddiff_lr3e-06] step 150: forget 1.643 retain +0.241 mia 0.978
[2026-10-25 06:31:12] [graddiff_lr3e-06] step 153: forget 1.711 retain +0.257 mia 0.976
[2026-10-25 06:31:17] [graddiff_lr3e-06] step 156: forget 1.773 retain +0.272 mia 0.974
[2026-10-25 06:31:21] [graddiff_lr3e-06] step 159: forget 1.835 retain +0.287 mia 0.972
[2026-10-25 06:31:26] [graddiff_lr3e-06] step 162: forget 1.908 retain +0.305 mia 0.969
[2026-10-25 06:31:30] [graddiff_lr3e-06] step 165: forget 1.988 retain +0.326 mia 0.966
[2026-10-25 06:31:35] [graddiff_lr3e-06] step 168: forget 2.080 retain +0.353 mia 0.963
[2026-10-25 06:31:39] [graddiff_lr3e-06] step 171: forget 2.166 retain +0.379 mia 0.960
[2026-10-25 06:31:44] [graddiff_lr3e-06] step 174: forget 2.253 retain +0.404 mia 0.957
[2026-10-25 06:31:48] [graddiff_lr3e-06] step 177: forget 2.338 retain +0.429 mia 0.952
[2026-10-25 06:31:53] [graddiff_lr3e-06] step 180: forget 2.428 retain +0.452 mia 0.948
[2026-10-25 06:31:57] [graddiff_lr3e-06] step 183: forget 2.531 retain +0.478 mia 0.943
[2026-10-25 06:32:02] [graddiff_lr3e-06] step 186: forget 2.641 retain +0.509 mia 0.937
[2026-10-25 06:32:06] [graddiff_lr3e-06] step 189: forget 2.765 retain +0.547 mia 0.930
[2026-10-25 06:32:11] [graddiff_lr3e-06] step 192: forget 2.873 retain +0.581 mia 0.924
[2026-10-25 06:32:15] [graddiff_lr3e-06] step 195: forget 2.969 retain +0.609 mia 0.917
[2026-10-25 06:32:19] [graddiff_lr3e-06] step 198: forget 3.061 retain +0.630 mia 0.911
[2026-10-25 06:32:24] [graddiff_lr3e-06] step 201: forget 3.162 retain +0.655 mia 0.903
[2026-10-25 06:32:28] [graddiff_lr3e-06] step 204: forget 3.264 retain +0.682 mia 0.895
[2026-10-25 06:32:33] [graddiff_lr3e-06] step 207: forget 3.387 retain +0.711 mia 0.884
[2026-10-25 06:32:37] [graddiff_lr3e-06] step 210: forget 3.527 retain +0.750 mia 0.872
[2026-10-25 06:32:42] [graddiff_lr3e-06] step 213: forget 3.672 retain +0.790 mia 0.861
[2026-10-25 06:32:46] [graddiff_lr3e-06] step 216: forget 3.849 retain +0.847 mia 0.846
[2026-10-25 06:32:51] [graddiff_lr3e-06] step 219: forget 4.026 retain +0.901 mia 0.831
[2026-10-25 06:32:55] [graddiff_lr3e-06] step 222: forget 4.208 retain +0.959 mia 0.816
[2026-10-25 06:33:00] [graddiff_lr3e-06] step 225: forget 4.397 retain +1.012 mia 0.800
[2026-10-25 06:33:04] [graddiff_lr3e-06] OPERATING POINT at step 225 (forget NLL reached the oracle's)
[2026-10-25 06:33:09] [graddiff_lr3e-06] step 228: forget 4.626 retain +1.073 mia 0.779
[2026-10-25 06:33:13] [graddiff_lr3e-06] step 231: forget 4.873 retain +1.144 mia 0.760
[2026-10-25 06:33:18] [graddiff_lr3e-06] step 234: forget 5.136 retain +1.222 mia 0.741
[2026-10-25 06:33:18] [graddiff_lr3e-06] finished: reached, op_step=225, promoted=True, 356s
[2026-10-25 06:33:22] [graddiff_lr1e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:33:27] [graddiff_lr1e-05] step 3: forget 0.273 retain +-0.000 mia 1.000
[2026-10-25 06:33:31] [graddiff_lr1e-05] step 6: forget 0.300 retain +0.006 mia 1.000
[2026-10-25 06:33:36] [graddiff_lr1e-05] step 9: forget 0.337 retain +0.012 mia 1.000
[2026-10-25 06:33:40] [graddiff_lr1e-05] step 12: forget 0.375 retain +0.022 mia 1.000
[2026-10-25 06:33:45] [graddiff_lr1e-05] step 15: forget 0.417 retain +0.034 mia 1.000
[2026-10-25 06:33:49] [graddiff_lr1e-05] step 18: forget 0.462 retain +0.047 mia 0.999
[2026-10-25 06:33:54] [graddiff_lr1e-05] step 21: forget 0.508 retain +0.059 mia 0.999
[2026-10-25 06:33:58] [graddiff_lr1e-05] step 24: forget 0.561 retain +0.072 mia 0.999
[2026-10-25 06:34:03] [graddiff_lr1e-05] step 27: forget 0.625 retain +0.086 mia 0.998
[2026-10-25 06:34:07] [graddiff_lr1e-05] step 30: forget 0.699 retain +0.107 mia 0.997
[2026-10-25 06:34:12] [graddiff_lr1e-05] step 33: forget 0.790 retain +0.132 mia 0.996
[2026-10-25 06:34:16] [graddiff_lr1e-05] step 36: forget 0.884 retain +0.155 mia 0.995
[2026-10-25 06:34:21] [graddiff_lr1e-05] step 39: forget 0.974 retain +0.174 mia 0.994
[2026-10-25 06:34:25] [graddiff_lr1e-05] step 42: forget 1.078 retain +0.194 mia 0.991
[2026-10-25 06:34:29] [graddiff_lr1e-05] step 45: forget 1.195 retain +0.223 mia 0.990
[2026-10-25 06:34:34] [graddiff_lr1e-05] step 48: forget 1.324 retain +0.254 mia 0.987
[2026-10-25 06:34:38] [graddiff_lr1e-05] step 51: forget 1.460 retain +0.283 mia 0.983
[2026-10-25 06:34:43] [graddiff_lr1e-05] step 54: forget 1.609 retain +0.320 mia 0.979
[2026-10-25 06:34:47] [graddiff_lr1e-05] step 57: forget 1.789 retain +0.371 mia 0.972
[2026-10-25 06:34:52] [graddiff_lr1e-05] step 60: forget 1.996 retain +0.429 mia 0.962
[2026-10-25 06:34:56] [graddiff_lr1e-05] step 63: forget 2.212 retain +0.496 mia 0.952
[2026-10-25 06:35:01] [graddiff_lr1e-05] step 66: forget 2.480 retain +0.586 mia 0.937
[2026-10-25 06:35:05] [graddiff_lr1e-05] step 69: forget 2.763 retain +0.686 mia 0.920
[2026-10-25 06:35:10] [graddiff_lr1e-05] step 72: forget 3.061 retain +0.799 mia 0.902
[2026-10-25 06:35:14] [graddiff_lr1e-05] step 75: forget 3.386 retain +0.931 mia 0.878
[2026-10-25 06:35:19] [graddiff_lr1e-05] step 78: forget 3.779 retain +1.097 mia 0.853
[2026-10-25 06:35:23] [graddiff_lr1e-05] step 81: forget 4.143 retain +1.239 mia 0.825
[2026-10-25 06:35:28] [graddiff_lr1e-05] step 84: forget 4.557 retain +1.414 mia 0.796
[2026-10-25 06:35:34] [graddiff_lr1e-05] OPERATING POINT at step 84 (forget NLL reached the oracle's)
[2026-10-25 06:35:38] [graddiff_lr1e-05] step 87: forget 5.202 retain +1.735 mia 0.752
[2026-10-25 06:35:42] [graddiff_lr1e-05] step 90: forget 6.148 retain +2.254 mia 0.692
[2026-10-25 06:35:47] [graddiff_lr1e-05] step 93: forget 7.200 retain +2.843 mia 0.638
[2026-10-25 06:35:47] [graddiff_lr1e-05] finished: reached, op_step=84, promoted=False, 148s
[2026-10-25 06:35:51] [graddiff_lr3e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:35:56] [graddiff_lr3e-05] step 3: forget 0.309 retain +0.011 mia 1.000
[2026-10-25 06:36:00] [graddiff_lr3e-05] step 6: forget 0.449 retain +0.064 mia 0.999
[2026-10-25 06:36:05] [graddiff_lr3e-05] step 9: forget 0.657 retain +0.152 mia 0.997
[2026-10-25 06:36:10] [graddiff_lr3e-05] step 12: forget 0.936 retain +0.272 mia 0.992
[2026-10-25 06:36:14] [graddiff_lr3e-05] step 15: forget 1.318 retain +0.420 mia 0.986
[2026-10-25 06:36:19] [graddiff_lr3e-05] step 18: forget 1.875 retain +0.646 mia 0.970
[2026-10-25 06:36:23] [graddiff_lr3e-05] step 21: forget 2.589 retain +0.957 mia 0.942
[2026-10-25 06:36:28] [graddiff_lr3e-05] step 24: forget 3.581 retain +1.435 mia 0.890
[2026-10-25 06:36:32] [graddiff_lr3e-05] step 27: forget 4.736 retain +1.965 mia 0.818
[2026-10-25 06:36:35] [graddiff_lr3e-05] OPERATING POINT at step 27 (forget NLL reached the oracle's)
[2026-10-25 06:36:40] [graddiff_lr3e-05] step 30: forget 6.465 retain +2.799 mia 0.699
[2026-10-25 06:36:44] [graddiff_lr3e-05] step 33: forget 10.778 retain +5.323 mia 0.554
[2026-10-25 06:36:49] [graddiff_lr3e-05] step 36: forget 17.565 retain +9.172 mia 0.461
[2026-10-25 06:36:49] [graddiff_lr3e-05] finished: reached, op_step=27, promoted=False, 60s
[2026-10-25 06:36:54] [npo_lr3e-06] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:36:58] [npo_lr3e-06] step 3: forget 0.269 retain +-0.000 mia 1.000
[2026-10-25 06:37:02] [npo_lr3e-06] step 6: forget 0.280 retain +0.001 mia 1.000
[2026-10-25 06:37:06] [npo_lr3e-06] step 9: forget 0.294 retain +0.002 mia 1.000
[2026-10-25 06:37:10] [npo_lr3e-06] step 12: forget 0.309 retain +0.003 mia 1.000
[2026-10-25 06:37:14] [npo_lr3e-06] step 15: forget 0.323 retain +0.005 mia 1.000
[2026-10-25 06:37:19] [npo_lr3e-06] step 18: forget 0.339 retain +0.007 mia 1.000
[2026-10-25 06:37:23] [npo_lr3e-06] step 21: forget 0.354 retain +0.009 mia 1.000
[2026-10-25 06:37:27] [npo_lr3e-06] step 24: forget 0.369 retain +0.011 mia 1.000
[2026-10-25 06:37:31] [npo_lr3e-06] step 27: forget 0.387 retain +0.014 mia 1.000
[2026-10-25 06:37:35] [npo_lr3e-06] step 30: forget 0.407 retain +0.019 mia 0.999
[2026-10-25 06:37:39] [npo_lr3e-06] step 33: forget 0.429 retain +0.024 mia 0.999
[2026-10-25 06:37:44] [npo_lr3e-06] step 36: forget 0.453 retain +0.030 mia 0.999
[2026-10-25 06:37:48] [npo_lr3e-06] step 39: forget 0.482 retain +0.040 mia 0.999
[2026-10-25 06:37:52] [npo_lr3e-06] step 42: forget 0.514 retain +0.053 mia 0.999
[2026-10-25 06:37:56] [npo_lr3e-06] step 45: forget 0.555 retain +0.073 mia 0.999
[2026-10-25 06:38:00] [npo_lr3e-06] step 48: forget 0.604 retain +0.102 mia 0.999
[2026-10-25 06:38:04] [npo_lr3e-06] step 51: forget 0.667 retain +0.142 mia 0.999
[2026-10-25 06:38:08] [npo_lr3e-06] step 54: forget 0.749 retain +0.200 mia 0.998
[2026-10-25 06:38:12] [npo_lr3e-06] step 57: forget 0.857 retain +0.282 mia 0.998
[2026-10-25 06:38:17] [npo_lr3e-06] step 60: forget 0.991 retain +0.388 mia 0.998
[2026-10-25 06:38:21] [npo_lr3e-06] step 63: forget 1.138 retain +0.510 mia 0.998
[2026-10-25 06:38:25] [npo_lr3e-06] step 66: forget 1.304 retain +0.648 mia 0.997
[2026-10-25 06:38:29] [npo_lr3e-06] step 69: forget 1.476 retain +0.791 mia 0.997
[2026-10-25 06:38:33] [npo_lr3e-06] step 72: forget 1.661 retain +0.944 mia 0.996
[2026-10-25 06:38:37] [npo_lr3e-06] step 75: forget 1.861 retain +1.113 mia 0.995
[2026-10-25 06:38:41] [npo_lr3e-06] step 78: forget 2.086 retain +1.302 mia 0.993
[2026-10-25 06:38:45] [npo_lr3e-06] step 81: forget 2.329 retain +1.506 mia 0.990
[2026-10-25 06:38:49] [npo_lr3e-06] step 84: forget 2.579 retain +1.717 mia 0.987
[2026-10-25 06:38:54] [npo_lr3e-06] step 87: forget 2.840 retain +1.937 mia 0.983
[2026-10-25 06:38:58] [npo_lr3e-06] step 90: forget 3.118 retain +2.175 mia 0.979
[2026-10-25 06:39:02] [npo_lr3e-06] step 93: forget 3.361 retain +2.385 mia 0.975
[2026-10-25 06:39:06] [npo_lr3e-06] step 96: forget 3.579 retain +2.575 mia 0.971
[2026-10-25 06:39:10] [npo_lr3e-06] step 99: forget 3.765 retain +2.737 mia 0.967
[2026-10-25 06:39:14] [npo_lr3e-06] step 102: forget 3.918 retain +2.874 mia 0.965
[2026-10-25 06:39:18] [npo_lr3e-06] step 105: forget 4.047 retain +2.987 mia 0.962
[2026-10-25 06:39:23] [npo_lr3e-06] step 108: forget 4.148 retain +3.075 mia 0.961
[2026-10-25 06:39:27] [npo_lr3e-06] step 111: forget 4.226 retain +3.143 mia 0.959
[2026-10-25 06:39:31] [npo_lr3e-06] step 114: forget 4.285 retain +3.195 mia 0.958
[2026-10-25 06:39:37] [npo_lr3e-06] OPERATING POINT at step 114 (forget NLL reached the oracle's)
[2026-10-25 06:39:41] [npo_lr3e-06] step 117: forget 4.334 retain +3.239 mia 0.957
[2026-10-25 06:39:45] [npo_lr3e-06] step 120: forget 4.373 retain +3.273 mia 0.957
[2026-10-25 06:39:49] [npo_lr3e-06] step 123: forget 4.403 retain +3.300 mia 0.956
[2026-10-25 06:39:49] [npo_lr3e-06] finished: reached, op_step=114, promoted=True, 178s
[2026-10-25 06:39:54] [npo_lr1e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:39:58] [npo_lr1e-05] step 3: forget 0.280 retain +0.001 mia 1.000
[2026-10-25 06:40:02] [npo_lr1e-05] step 6: forget 0.328 retain +0.011 mia 1.000
[2026-10-25 06:40:07] [npo_lr1e-05] step 9: forget 0.389 retain +0.027 mia 0.999
[2026-10-25 06:40:11] [npo_lr1e-05] step 12: forget 0.464 retain +0.054 mia 0.999
[2026-10-25 06:40:15] [npo_lr1e-05] step 15: forget 0.572 retain +0.106 mia 0.998
[2026-10-25 06:40:19] [npo_lr1e-05] step 18: forget 0.757 retain +0.222 mia 0.997
[2026-10-25 06:40:24] [npo_lr1e-05] step 21: forget 1.075 retain +0.457 mia 0.996
[2026-10-25 06:40:28] [npo_lr1e-05] step 24: forget 1.549 retain +0.843 mia 0.993
[2026-10-25 06:40:32] [npo_lr1e-05] step 27: forget 2.120 retain +1.321 mia 0.989
[2026-10-25 06:40:36] [npo_lr1e-05] step 30: forget 2.795 retain +1.886 mia 0.984
[2026-10-25 06:40:40] [npo_lr1e-05] step 33: forget 3.664 retain +2.621 mia 0.972
[2026-10-25 06:40:44] [npo_lr1e-05] step 36: forget 4.603 retain +3.436 mia 0.958
[2026-10-25 06:40:47] [npo_lr1e-05] OPERATING POINT at step 36 (forget NLL reached the oracle's)
[2026-10-25 06:40:51] [npo_lr1e-05] step 39: forget 5.566 retain +4.305 mia 0.944
[2026-10-25 06:40:55] [npo_lr1e-05] step 42: forget 6.365 retain +5.037 mia 0.933
[2026-10-25 06:41:00] [npo_lr1e-05] step 45: forget 6.998 retain +5.624 mia 0.924
[2026-10-25 06:41:00] [npo_lr1e-05] finished: reached, op_step=36, promoted=False, 69s
[2026-10-25 06:41:05] [npo_lr3e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:41:09] [npo_lr3e-05] step 3: forget 0.331 retain +0.014 mia 1.000
[2026-10-25 06:41:13] [npo_lr3e-05] step 6: forget 0.625 retain +0.159 mia 0.996
[2026-10-25 06:41:17] [npo_lr3e-05] step 9: forget 1.413 retain +0.740 mia 0.987
[2026-10-25 06:41:21] [npo_lr3e-05] step 12: forget 3.015 retain +2.064 mia 0.965
[2026-10-25 06:41:26] [npo_lr3e-05] step 15: forget 5.788 retain +4.539 mia 0.920
[2026-10-25 06:41:30] [npo_lr3e-05] OPERATING POINT at step 15 (forget NLL reached the oracle's)
[2026-10-25 06:41:34] [npo_lr3e-05] step 18: forget 8.772 retain +7.314 mia 0.872
[2026-10-25 06:41:39] [npo_lr3e-05] step 21: forget 11.491 retain +9.849 mia 0.824
[2026-10-25 06:41:43] [npo_lr3e-05] step 24: forget 13.798 retain +12.007 mia 0.789
[2026-10-25 06:41:43] [npo_lr3e-05] finished: reached, op_step=15, promoted=False, 41s
[2026-10-25 06:41:48] [npo_rt_lr3e-06] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:41:53] [npo_rt_lr3e-06] step 3: forget 0.269 retain +-0.000 mia 1.000
[2026-10-25 06:41:57] [npo_rt_lr3e-06] step 6: forget 0.280 retain +0.001 mia 1.000
[2026-10-25 06:42:02] [npo_rt_lr3e-06] step 9: forget 0.293 retain +0.002 mia 1.000
[2026-10-25 06:42:07] [npo_rt_lr3e-06] step 12: forget 0.309 retain +0.003 mia 1.000
[2026-10-25 06:42:12] [npo_rt_lr3e-06] step 15: forget 0.324 retain +0.005 mia 1.000
[2026-10-25 06:42:16] [npo_rt_lr3e-06] step 18: forget 0.340 retain +0.007 mia 1.000
[2026-10-25 06:42:21] [npo_rt_lr3e-06] step 21: forget 0.356 retain +0.008 mia 1.000
[2026-10-25 06:42:26] [npo_rt_lr3e-06] step 24: forget 0.373 retain +0.011 mia 1.000
[2026-10-25 06:42:30] [npo_rt_lr3e-06] step 27: forget 0.392 retain +0.015 mia 1.000
[2026-10-25 06:42:35] [npo_rt_lr3e-06] step 30: forget 0.412 retain +0.019 mia 0.999
[2026-10-25 06:42:40] [npo_rt_lr3e-06] step 33: forget 0.436 retain +0.024 mia 0.999
[2026-10-25 06:42:44] [npo_rt_lr3e-06] step 36: forget 0.462 retain +0.030 mia 0.999
[2026-10-25 06:42:49] [npo_rt_lr3e-06] step 39: forget 0.490 retain +0.038 mia 0.999
[2026-10-25 06:42:54] [npo_rt_lr3e-06] step 42: forget 0.522 retain +0.048 mia 0.999
[2026-10-25 06:42:58] [npo_rt_lr3e-06] step 45: forget 0.559 retain +0.062 mia 0.998
[2026-10-25 06:43:03] [npo_rt_lr3e-06] step 48: forget 0.603 retain +0.082 mia 0.998
[2026-10-25 06:43:08] [npo_rt_lr3e-06] step 51: forget 0.655 retain +0.110 mia 0.998
[2026-10-25 06:43:12] [npo_rt_lr3e-06] step 54: forget 0.719 retain +0.147 mia 0.997
[2026-10-25 06:43:17] [npo_rt_lr3e-06] step 57: forget 0.797 retain +0.196 mia 0.997
[2026-10-25 06:43:22] [npo_rt_lr3e-06] step 60: forget 0.898 retain +0.266 mia 0.996
[2026-10-25 06:43:26] [npo_rt_lr3e-06] step 63: forget 1.020 retain +0.356 mia 0.996
[2026-10-25 06:43:31] [npo_rt_lr3e-06] step 66: forget 1.157 retain +0.459 mia 0.996
[2026-10-25 06:43:36] [npo_rt_lr3e-06] step 69: forget 1.308 retain +0.576 mia 0.996
[2026-10-25 06:43:40] [npo_rt_lr3e-06] step 72: forget 1.464 retain +0.699 mia 0.995
[2026-10-25 06:43:45] [npo_rt_lr3e-06] step 75: forget 1.623 retain +0.825 mia 0.994
[2026-10-25 06:43:49] [npo_rt_lr3e-06] step 78: forget 1.768 retain +0.936 mia 0.993
[2026-10-25 06:43:54] [npo_rt_lr3e-06] step 81: forget 1.871 retain +1.008 mia 0.993
[2026-10-25 06:43:59] [npo_rt_lr3e-06] step 84: forget 1.937 retain +1.047 mia 0.992
[2026-10-25 06:44:03] [npo_rt_lr3e-06] step 87: forget 1.940 retain +1.030 mia 0.992
[2026-10-25 06:44:08] [npo_rt_lr3e-06] step 90: forget 1.929 retain +0.999 mia 0.991
[2026-10-25 06:44:13] [npo_rt_lr3e-06] step 93: forget 1.899 retain +0.953 mia 0.991
[2026-10-25 06:44:17] [npo_rt_lr3e-06] step 96: forget 1.857 retain +0.896 mia 0.991
[2026-10-25 06:44:22] [npo_rt_lr3e-06] step 99: forget 1.824 retain +0.847 mia 0.991
[2026-10-25 06:44:26] [npo_rt_lr3e-06] step 102: forget 1.796 retain +0.808 mia 0.991
[2026-10-25 06:44:31] [npo_rt_lr3e-06] step 105: forget 1.773 retain +0.772 mia 0.991
[2026-10-25 06:44:36] [npo_rt_lr3e-06] step 108: forget 1.748 retain +0.732 mia 0.991
[2026-10-25 06:44:41] [npo_rt_lr3e-06] step 111: forget 1.725 retain +0.691 mia 0.990
[2026-10-25 06:44:45] [npo_rt_lr3e-06] step 114: forget 1.709 retain +0.655 mia 0.990
[2026-10-25 06:44:50] [npo_rt_lr3e-06] step 117: forget 1.706 retain +0.629 mia 0.990
[2026-10-25 06:44:54] [npo_rt_lr3e-06] step 120: forget 1.710 retain +0.609 mia 0.989
[2026-10-25 06:44:59] [npo_rt_lr3e-06] step 123: forget 1.712 retain +0.585 mia 0.989
[2026-10-25 06:45:04] [npo_rt_lr3e-06] step 126: forget 1.722 retain +0.571 mia 0.988
[2026-10-25 06:45:08] [npo_rt_lr3e-06] step 129: forget 1.745 retain +0.563 mia 0.987
[2026-10-25 06:45:13] [npo_rt_lr3e-06] step 132: forget 1.769 retain +0.556 mia 0.987
[2026-10-25 06:45:18] [npo_rt_lr3e-06] step 135: forget 1.794 retain +0.547 mia 0.987
[2026-10-25 06:45:23] [npo_rt_lr3e-06] step 138: forget 1.809 retain +0.530 mia 0.986
[2026-10-25 06:45:27] [npo_rt_lr3e-06] step 141: forget 1.819 retain +0.505 mia 0.985
[2026-10-25 06:45:32] [npo_rt_lr3e-06] step 144: forget 1.826 retain +0.480 mia 0.985
[2026-10-25 06:45:37] [npo_rt_lr3e-06] step 147: forget 1.823 retain +0.446 mia 0.984
[2026-10-25 06:45:41] [npo_rt_lr3e-06] step 150: forget 1.825 retain +0.419 mia 0.984
[2026-10-25 06:45:46] [npo_rt_lr3e-06] step 153: forget 1.821 retain +0.390 mia 0.983
[2026-10-25 06:45:51] [npo_rt_lr3e-06] step 156: forget 1.808 retain +0.358 mia 0.983
[2026-10-25 06:45:56] [npo_rt_lr3e-06] step 159: forget 1.801 retain +0.331 mia 0.982
[2026-10-25 06:46:00] [npo_rt_lr3e-06] step 162: forget 1.801 retain +0.310 mia 0.982
[2026-10-25 06:46:05] [npo_rt_lr3e-06] step 165: forget 1.821 retain +0.304 mia 0.981
[2026-10-25 06:46:10] [npo_rt_lr3e-06] step 168: forget 1.844 retain +0.298 mia 0.980
[2026-10-25 06:46:14] [npo_rt_lr3e-06] step 171: forget 1.852 retain +0.283 mia 0.980
[2026-10-25 06:46:19] [npo_rt_lr3e-06] step 174: forget 1.868 retain +0.273 mia 0.979
[2026-10-25 06:46:24] [npo_rt_lr3e-06] step 177: forget 1.887 retain +0.269 mia 0.979
[2026-10-25 06:46:29] [npo_rt_lr3e-06] step 180: forget 1.893 retain +0.256 mia 0.979
[2026-10-25 06:46:34] [npo_rt_lr3e-06] step 183: forget 1.894 retain +0.244 mia 0.979
[2026-10-25 06:46:38] [npo_rt_lr3e-06] step 186: forget 1.905 retain +0.236 mia 0.978
[2026-10-25 06:46:43] [npo_rt_lr3e-06] step 189: forget 1.920 retain +0.230 mia 0.978
[2026-10-25 06:46:48] [npo_rt_lr3e-06] step 192: forget 1.944 retain +0.228 mia 0.977
[2026-10-25 06:46:52] [npo_rt_lr3e-06] step 195: forget 1.964 retain +0.225 mia 0.976
[2026-10-25 06:46:57] [npo_rt_lr3e-06] step 198: forget 1.981 retain +0.220 mia 0.975
[2026-10-25 06:47:02] [npo_rt_lr3e-06] step 201: forget 2.000 retain +0.215 mia 0.974
[2026-10-25 06:47:06] [npo_rt_lr3e-06] step 204: forget 2.012 retain +0.210 mia 0.973
[2026-10-25 06:47:11] [npo_rt_lr3e-06] step 207: forget 2.019 retain +0.204 mia 0.973
[2026-10-25 06:47:16] [npo_rt_lr3e-06] step 210: forget 2.016 retain +0.195 mia 0.972
[2026-10-25 06:47:20] [npo_rt_lr3e-06] step 213: forget 2.005 retain +0.184 mia 0.972
[2026-10-25 06:47:25] [npo_rt_lr3e-06] step 216: forget 2.004 retain +0.177 mia 0.972
[2026-10-25 06:47:30] [npo_rt_lr3e-06] step 219: forget 2.010 retain +0.173 mia 0.971
[2026-10-25 06:47:35] [npo_rt_lr3e-06] step 222: forget 2.026 retain +0.173 mia 0.970
[2026-10-25 06:47:39] [npo_rt_lr3e-06] step 225: forget 2.033 retain +0.167 mia 0.969
[2026-10-25 06:47:44] [npo_rt_lr3e-06] step 228: forget 2.046 retain +0.163 mia 0.969
[2026-10-25 06:47:49] [npo_rt_lr3e-06] step 231: forget 2.063 retain +0.160 mia 0.967
[2026-10-25 06:47:53] [npo_rt_lr3e-06] step 234: forget 2.083 retain +0.158 mia 0.966
[2026-10-25 06:47:58] [npo_rt_lr3e-06] step 237: forget 2.098 retain +0.156 mia 0.964
[2026-10-25 06:48:03] [npo_rt_lr3e-06] step 240: forget 2.113 retain +0.155 mia 0.963
[2026-10-25 06:48:08] [npo_rt_lr3e-06] finished: never_reached, op_step=None, promoted=True, 383s
[2026-10-25 06:48:13] [npo_rt_lr1e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:48:17] [npo_rt_lr1e-05] step 3: forget 0.279 retain +0.001 mia 1.000
[2026-10-25 06:48:22] [npo_rt_lr1e-05] step 6: forget 0.320 retain +0.012 mia 1.000
[2026-10-25 06:48:27] [npo_rt_lr1e-05] step 9: forget 0.378 retain +0.026 mia 0.999
[2026-10-25 06:48:31] [npo_rt_lr1e-05] step 12: forget 0.444 retain +0.047 mia 0.999
[2026-10-25 06:48:36] [npo_rt_lr1e-05] step 15: forget 0.537 retain +0.088 mia 0.998
[2026-10-25 06:48:41] [npo_rt_lr1e-05] step 18: forget 0.676 retain +0.169 mia 0.998
[2026-10-25 06:48:46] [npo_rt_lr1e-05] step 21: forget 0.930 retain +0.345 mia 0.997
[2026-10-25 06:48:51] [npo_rt_lr1e-05] step 24: forget 1.345 retain +0.664 mia 0.995
[2026-10-25 06:48:55] [npo_rt_lr1e-05] step 27: forget 1.849 retain +1.058 mia 0.992
[2026-10-25 06:49:00] [npo_rt_lr1e-05] step 30: forget 2.200 retain +1.307 mia 0.989
[2026-10-25 06:49:05] [npo_rt_lr1e-05] step 33: forget 2.332 retain +1.356 mia 0.987
[2026-10-25 06:49:09] [npo_rt_lr1e-05] step 36: forget 2.300 retain +1.266 mia 0.987
[2026-10-25 06:49:14] [npo_rt_lr1e-05] step 39: forget 2.207 retain +1.135 mia 0.988
[2026-10-25 06:49:19] [npo_rt_lr1e-05] step 42: forget 2.074 retain +0.993 mia 0.989
[2026-10-25 06:49:23] [npo_rt_lr1e-05] step 45: forget 1.902 retain +0.815 mia 0.991
[2026-10-25 06:49:28] [npo_rt_lr1e-05] step 48: forget 1.836 retain +0.724 mia 0.990
[2026-10-25 06:49:33] [npo_rt_lr1e-05] step 51: forget 1.830 retain +0.678 mia 0.989
[2026-10-25 06:49:37] [npo_rt_lr1e-05] step 54: forget 1.830 retain +0.630 mia 0.987
[2026-10-25 06:49:42] [npo_rt_lr1e-05] step 57: forget 1.814 retain +0.562 mia 0.985
[2026-10-25 06:49:47] [npo_rt_lr1e-05] step 60: forget 1.824 retain +0.501 mia 0.984
[2026-10-25 06:49:51] [npo_rt_lr1e-05] step 63: forget 1.853 retain +0.443 mia 0.981
[2026-10-25 06:49:56] [npo_rt_lr1e-05] step 66: forget 1.929 retain +0.409 mia 0.976
[2026-10-25 06:50:01] [npo_rt_lr1e-05] step 69: forget 2.018 retain +0.381 mia 0.972
[2026-10-25 06:50:05] [npo_rt_lr1e-05] step 72: forget 2.118 retain +0.363 mia 0.969
[2026-10-25 06:50:10] [npo_rt_lr1e-05] step 75: forget 2.246 retain +0.367 mia 0.964
[2026-10-25 06:50:15] [npo_rt_lr1e-05] step 78: forget 2.286 retain +0.335 mia 0.963
[2026-10-25 06:50:19] [npo_rt_lr1e-05] step 81: forget 2.242 retain +0.280 mia 0.963
[2026-10-25 06:50:24] [npo_rt_lr1e-05] step 84: forget 2.172 retain +0.233 mia 0.965
[2026-10-25 06:50:29] [npo_rt_lr1e-05] step 87: forget 2.117 retain +0.201 mia 0.965
[2026-10-25 06:50:33] [npo_rt_lr1e-05] step 90: forget 2.106 retain +0.179 mia 0.964
[2026-10-25 06:50:38] [npo_rt_lr1e-05] step 93: forget 2.129 retain +0.166 mia 0.961
[2026-10-25 06:50:43] [npo_rt_lr1e-05] step 96: forget 2.199 retain +0.165 mia 0.955
[2026-10-25 06:50:47] [npo_rt_lr1e-05] step 99: forget 2.291 retain +0.175 mia 0.948
[2026-10-25 06:50:52] [npo_rt_lr1e-05] step 102: forget 2.384 retain +0.188 mia 0.944
[2026-10-25 06:50:57] [npo_rt_lr1e-05] step 105: forget 2.406 retain +0.184 mia 0.941
[2026-10-25 06:51:02] [npo_rt_lr1e-05] step 108: forget 2.397 retain +0.176 mia 0.939
[2026-10-25 06:51:06] [npo_rt_lr1e-05] step 111: forget 2.368 retain +0.157 mia 0.940
[2026-10-25 06:51:11] [npo_rt_lr1e-05] step 114: forget 2.344 retain +0.140 mia 0.939
[2026-10-25 06:51:16] [npo_rt_lr1e-05] step 117: forget 2.326 retain +0.128 mia 0.939
[2026-10-25 06:51:20] [npo_rt_lr1e-05] step 120: forget 2.323 retain +0.119 mia 0.937
[2026-10-25 06:51:25] [npo_rt_lr1e-05] step 123: forget 2.327 retain +0.113 mia 0.936
[2026-10-25 06:51:29] [npo_rt_lr1e-05] step 126: forget 2.344 retain +0.109 mia 0.935
[2026-10-25 06:51:34] [npo_rt_lr1e-05] step 129: forget 2.352 retain +0.103 mia 0.933
[2026-10-25 06:51:39] [npo_rt_lr1e-05] step 132: forget 2.363 retain +0.098 mia 0.932
[2026-10-25 06:51:43] [npo_rt_lr1e-05] step 135: forget 2.369 retain +0.097 mia 0.929
[2026-10-25 06:51:48] [npo_rt_lr1e-05] step 138: forget 2.386 retain +0.096 mia 0.926
[2026-10-25 06:51:53] [npo_rt_lr1e-05] step 141: forget 2.436 retain +0.097 mia 0.921
[2026-10-25 06:51:57] [npo_rt_lr1e-05] step 144: forget 2.481 retain +0.098 mia 0.915
[2026-10-25 06:52:02] [npo_rt_lr1e-05] step 147: forget 2.515 retain +0.102 mia 0.912
[2026-10-25 06:52:07] [npo_rt_lr1e-05] step 150: forget 2.537 retain +0.105 mia 0.911
[2026-10-25 06:52:12] [npo_rt_lr1e-05] step 153: forget 2.534 retain +0.101 mia 0.911
[2026-10-25 06:52:16] [npo_rt_lr1e-05] step 156: forget 2.525 retain +0.100 mia 0.910
[2026-10-25 06:52:21] [npo_rt_lr1e-05] step 159: forget 2.497 retain +0.092 mia 0.913
[2026-10-25 06:52:26] [npo_rt_lr1e-05] step 162: forget 2.479 retain +0.090 mia 0.912
[2026-10-25 06:52:30] [npo_rt_lr1e-05] step 165: forget 2.490 retain +0.091 mia 0.912
[2026-10-25 06:52:35] [npo_rt_lr1e-05] step 168: forget 2.497 retain +0.090 mia 0.913
[2026-10-25 06:52:40] [npo_rt_lr1e-05] step 171: forget 2.487 retain +0.086 mia 0.914
[2026-10-25 06:52:45] [npo_rt_lr1e-05] step 174: forget 2.472 retain +0.081 mia 0.917
[2026-10-25 06:52:49] [npo_rt_lr1e-05] step 177: forget 2.474 retain +0.077 mia 0.915
[2026-10-25 06:52:54] [npo_rt_lr1e-05] step 180: forget 2.468 retain +0.072 mia 0.915
[2026-10-25 06:52:59] [npo_rt_lr1e-05] step 183: forget 2.467 retain +0.069 mia 0.914
[2026-10-25 06:53:03] [npo_rt_lr1e-05] step 186: forget 2.473 retain +0.068 mia 0.913
[2026-10-25 06:53:08] [npo_rt_lr1e-05] step 189: forget 2.482 retain +0.066 mia 0.911
[2026-10-25 06:53:13] [npo_rt_lr1e-05] step 192: forget 2.502 retain +0.065 mia 0.910
[2026-10-25 06:53:17] [npo_rt_lr1e-05] step 195: forget 2.528 retain +0.064 mia 0.907
[2026-10-25 06:53:22] [npo_rt_lr1e-05] step 198: forget 2.543 retain +0.063 mia 0.906
[2026-10-25 06:53:27] [npo_rt_lr1e-05] step 201: forget 2.564 retain +0.061 mia 0.903
[2026-10-25 06:53:31] [npo_rt_lr1e-05] step 204: forget 2.577 retain +0.061 mia 0.901
[2026-10-25 06:53:36] [npo_rt_lr1e-05] step 207: forget 2.592 retain +0.057 mia 0.898
[2026-10-25 06:53:41] [npo_rt_lr1e-05] step 210: forget 2.604 retain +0.056 mia 0.896
[2026-10-25 06:53:45] [npo_rt_lr1e-05] step 213: forget 2.614 retain +0.054 mia 0.895
[2026-10-25 06:53:50] [npo_rt_lr1e-05] step 216: forget 2.625 retain +0.052 mia 0.893
[2026-10-25 06:53:55] [npo_rt_lr1e-05] step 219: forget 2.634 retain +0.052 mia 0.892
[2026-10-25 06:54:00] [npo_rt_lr1e-05] step 222: forget 2.633 retain +0.052 mia 0.890
[2026-10-25 06:54:04] [npo_rt_lr1e-05] step 225: forget 2.629 retain +0.050 mia 0.890
[2026-10-25 06:54:09] [npo_rt_lr1e-05] step 228: forget 2.645 retain +0.049 mia 0.887
[2026-10-25 06:54:14] [npo_rt_lr1e-05] step 231: forget 2.673 retain +0.050 mia 0.882
[2026-10-25 06:54:18] [npo_rt_lr1e-05] step 234: forget 2.692 retain +0.049 mia 0.880
[2026-10-25 06:54:23] [npo_rt_lr1e-05] step 237: forget 2.702 retain +0.050 mia 0.879
[2026-10-25 06:54:28] [npo_rt_lr1e-05] step 240: forget 2.711 retain +0.051 mia 0.877
[2026-10-25 06:54:31] [npo_rt_lr1e-05] finished: never_reached, op_step=None, promoted=True, 381s
[2026-10-25 06:54:36] [npo_rt_lr3e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 06:54:41] [npo_rt_lr3e-05] step 3: forget 0.331 retain +0.012 mia 1.000
[2026-10-25 06:54:45] [npo_rt_lr3e-05] step 6: forget 0.613 retain +0.144 mia 0.996
[2026-10-25 06:54:50] [npo_rt_lr3e-05] step 9: forget 1.325 retain +0.648 mia 0.990
[2026-10-25 06:54:55] [npo_rt_lr3e-05] step 12: forget 2.719 retain +1.738 mia 0.973
[2026-10-25 06:55:00] [npo_rt_lr3e-05] step 15: forget 3.282 retain +2.040 mia 0.964
[2026-10-25 06:55:04] [npo_rt_lr3e-05] step 18: forget 2.692 retain +1.410 mia 0.969
[2026-10-25 06:55:09] [npo_rt_lr3e-05] step 21: forget 2.283 retain +1.057 mia 0.971
[2026-10-25 06:55:14] [npo_rt_lr3e-05] step 24: forget 2.241 retain +0.979 mia 0.969
[2026-10-25 06:55:19] [npo_rt_lr3e-05] step 27: forget 2.345 retain +0.985 mia 0.964
[2026-10-25 06:55:23] [npo_rt_lr3e-05] step 30: forget 2.309 retain +0.872 mia 0.960
[2026-10-25 06:55:28] [npo_rt_lr3e-05] step 33: forget 2.219 retain +0.693 mia 0.955
[2026-10-25 06:55:33] [npo_rt_lr3e-05] step 36: forget 2.134 retain +0.515 mia 0.948
[2026-10-25 06:55:37] [npo_rt_lr3e-05] step 39: forget 2.235 retain +0.472 mia 0.939
[2026-10-25 06:55:42] [npo_rt_lr3e-05] step 42: forget 2.453 retain +0.492 mia 0.922
[2026-10-25 06:55:47] [npo_rt_lr3e-05] step 45: forget 2.743 retain +0.538 mia 0.900
[2026-10-25 06:55:51] [npo_rt_lr3e-05] step 48: forget 3.053 retain +0.599 mia 0.876
[2026-10-25 06:55:56] [npo_rt_lr3e-05] step 51: forget 3.269 retain +0.616 mia 0.849
[2026-10-25 06:56:00] [npo_rt_lr3e-05] step 54: forget 3.229 retain +0.514 mia 0.835
[2026-10-25 06:56:05] [npo_rt_lr3e-05] step 57: forget 3.146 retain +0.436 mia 0.830
[2026-10-25 06:56:10] [npo_rt_lr3e-05] step 60: forget 3.070 retain +0.385 mia 0.832
[2026-10-25 06:56:14] [npo_rt_lr3e-05] step 63: forget 2.997 retain +0.359 mia 0.838
[2026-10-25 06:56:19] [npo_rt_lr3e-05] step 66: forget 2.964 retain +0.349 mia 0.843
[2026-10-25 06:56:24] [npo_rt_lr3e-05] step 69: forget 2.952 retain +0.339 mia 0.846
[2026-10-25 06:56:28] [npo_rt_lr3e-05] step 72: forget 2.960 retain +0.337 mia 0.849
[2026-10-25 06:56:33] [npo_rt_lr3e-05] step 75: forget 3.013 retain +0.338 mia 0.849
[2026-10-25 06:56:38] [npo_rt_lr3e-05] step 78: forget 3.034 retain +0.327 mia 0.844
[2026-10-25 06:56:42] [npo_rt_lr3e-05] step 81: forget 2.993 retain +0.305 mia 0.847
[2026-10-25 06:56:47] [npo_rt_lr3e-05] step 84: forget 2.942 retain +0.299 mia 0.849
[2026-10-25 06:56:52] [npo_rt_lr3e-05] step 87: forget 2.903 retain +0.296 mia 0.850
[2026-10-25 06:56:56] [npo_rt_lr3e-05] step 90: forget 2.907 retain +0.297 mia 0.848
[2026-10-25 06:57:01] [npo_rt_lr3e-05] step 93: forget 2.916 retain +0.292 mia 0.844
[2026-10-25 06:57:06] [npo_rt_lr3e-05] step 96: forget 2.954 retain +0.294 mia 0.837
[2026-10-25 06:57:10] [npo_rt_lr3e-05] step 99: forget 3.020 retain +0.292 mia 0.829
[2026-10-25 06:57:15] [npo_rt_lr3e-05] step 102: forget 3.073 retain +0.289 mia 0.824
[2026-10-25 06:57:20] [npo_rt_lr3e-05] step 105: forget 3.104 retain +0.295 mia 0.824
[2026-10-25 06:57:25] [npo_rt_lr3e-05] step 108: forget 3.103 retain +0.294 mia 0.828
[2026-10-25 06:57:29] [npo_rt_lr3e-05] step 111: forget 3.074 retain +0.276 mia 0.831
[2026-10-25 06:57:34] [npo_rt_lr3e-05] step 114: forget 3.060 retain +0.259 mia 0.834
[2026-10-25 06:57:39] [npo_rt_lr3e-05] step 117: forget 3.063 retain +0.251 mia 0.831
[2026-10-25 06:57:43] [npo_rt_lr3e-05] step 120: forget 3.047 retain +0.246 mia 0.834
[2026-10-25 06:57:48] [npo_rt_lr3e-05] step 123: forget 3.034 retain +0.239 mia 0.835
[2026-10-25 06:57:53] [npo_rt_lr3e-05] step 126: forget 3.037 retain +0.238 mia 0.837
[2026-10-25 06:57:57] [npo_rt_lr3e-05] step 129: forget 3.048 retain +0.241 mia 0.839
[2026-10-25 06:58:02] [npo_rt_lr3e-05] step 132: forget 3.027 retain +0.243 mia 0.845
[2026-10-25 06:58:07] [npo_rt_lr3e-05] step 135: forget 3.018 retain +0.250 mia 0.848
[2026-10-25 06:58:11] [npo_rt_lr3e-05] step 138: forget 3.009 retain +0.256 mia 0.847
[2026-10-25 06:58:16] [npo_rt_lr3e-05] step 141: forget 3.015 retain +0.260 mia 0.845
[2026-10-25 06:58:21] [npo_rt_lr3e-05] step 144: forget 3.051 retain +0.267 mia 0.845
[2026-10-25 06:58:25] [npo_rt_lr3e-05] step 147: forget 3.081 retain +0.270 mia 0.846
[2026-10-25 06:58:30] [npo_rt_lr3e-05] step 150: forget 3.096 retain +0.262 mia 0.846
[2026-10-25 06:58:35] [npo_rt_lr3e-05] step 153: forget 3.076 retain +0.257 mia 0.846
[2026-10-25 06:58:39] [npo_rt_lr3e-05] step 156: forget 3.047 retain +0.255 mia 0.849
[2026-10-25 06:58:44] [npo_rt_lr3e-05] step 159: forget 3.020 retain +0.254 mia 0.852
[2026-10-25 06:58:49] [npo_rt_lr3e-05] step 162: forget 3.008 retain +0.252 mia 0.852
[2026-10-25 06:58:53] [npo_rt_lr3e-05] step 165: forget 3.027 retain +0.258 mia 0.850
[2026-10-25 06:58:58] [npo_rt_lr3e-05] step 168: forget 3.047 retain +0.265 mia 0.844
[2026-10-25 06:59:03] [npo_rt_lr3e-05] step 171: forget 3.042 retain +0.254 mia 0.840
[2026-10-25 06:59:07] [npo_rt_lr3e-05] step 174: forget 3.051 retain +0.243 mia 0.838
[2026-10-25 06:59:12] [npo_rt_lr3e-05] step 177: forget 3.069 retain +0.240 mia 0.832
[2026-10-25 06:59:17] [npo_rt_lr3e-05] step 180: forget 3.073 retain +0.238 mia 0.832
[2026-10-25 06:59:21] [npo_rt_lr3e-05] step 183: forget 3.068 retain +0.241 mia 0.835
[2026-10-25 06:59:26] [npo_rt_lr3e-05] step 186: forget 3.086 retain +0.243 mia 0.837
[2026-10-25 06:59:31] [npo_rt_lr3e-05] step 189: forget 3.120 retain +0.239 mia 0.831
[2026-10-25 06:59:36] [npo_rt_lr3e-05] step 192: forget 3.164 retain +0.241 mia 0.823
[2026-10-25 06:59:40] [npo_rt_lr3e-05] step 195: forget 3.182 retain +0.252 mia 0.819
[2026-10-25 06:59:45] [npo_rt_lr3e-05] step 198: forget 3.174 retain +0.262 mia 0.821
[2026-10-25 06:59:50] [npo_rt_lr3e-05] step 201: forget 3.151 retain +0.263 mia 0.823
[2026-10-25 06:59:54] [npo_rt_lr3e-05] step 204: forget 3.145 retain +0.270 mia 0.822
[2026-10-25 06:59:59] [npo_rt_lr3e-05] step 207: forget 3.152 retain +0.270 mia 0.822
[2026-10-25 07:00:04] [npo_rt_lr3e-05] step 210: forget 3.158 retain +0.268 mia 0.822
[2026-10-25 07:00:08] [npo_rt_lr3e-05] step 213: forget 3.171 retain +0.265 mia 0.819
[2026-10-25 07:00:13] [npo_rt_lr3e-05] step 216: forget 3.177 retain +0.257 mia 0.816
[2026-10-25 07:00:18] [npo_rt_lr3e-05] step 219: forget 3.198 retain +0.248 mia 0.813
[2026-10-25 07:00:22] [npo_rt_lr3e-05] step 222: forget 3.203 retain +0.257 mia 0.813
[2026-10-25 07:00:27] [npo_rt_lr3e-05] step 225: forget 3.190 retain +0.253 mia 0.815
[2026-10-25 07:00:32] [npo_rt_lr3e-05] step 228: forget 3.181 retain +0.238 mia 0.816
[2026-10-25 07:00:36] [npo_rt_lr3e-05] step 231: forget 3.172 retain +0.230 mia 0.815
[2026-10-25 07:00:41] [npo_rt_lr3e-05] step 234: forget 3.190 retain +0.232 mia 0.811
[2026-10-25 07:00:45] [npo_rt_lr3e-05] step 237: forget 3.184 retain +0.228 mia 0.809
[2026-10-25 07:00:50] [npo_rt_lr3e-05] step 240: forget 3.193 retain +0.224 mia 0.807
[2026-10-25 07:01:02] [npo_rt_lr3e-05] finished: never_reached, op_step=None, promoted=True, 388s
[2026-10-25 07:01:06] [retainft_lr1e-05] start: forget 0.263 retain 0.284 (oracle forget target 4.279)
[2026-10-25 07:01:10] [retainft_lr1e-05] step 3: forget 0.265 retain +-0.000 mia 1.000
[2026-10-25 07:01:14] [retainft_lr1e-05] step 6: forget 0.272 retain +0.006 mia 1.000
[2026-10-25 07:01:18] [retainft_lr1e-05] step 9: forget 0.282 retain +0.014 mia 1.000
[2026-10-25 07:01:22] [retainft_lr1e-05] step 12: forget 0.288 retain +0.020 mia 1.000
[2026-10-25 07:01:26] [retainft_lr1e-05] step 15: forget 0.294 retain +0.025 mia 1.000
[2026-10-25 07:01:30] [retainft_lr1e-05] step 18: forget 0.298 retain +0.029 mia 1.000
[2026-10-25 07:01:34] [retainft_lr1e-05] step 21: forget 0.300 retain +0.030 mia 1.000
[2026-10-25 07:01:39] [retainft_lr1e-05] step 24: forget 0.301 retain +0.031 mia 1.000
[2026-10-25 07:01:43] [retainft_lr1e-05] step 27: forget 0.303 retain +0.031 mia 1.000
[2026-10-25 07:01:47] [retainft_lr1e-05] step 30: forget 0.303 retain +0.031 mia 1.000
[2026-10-25 07:01:51] [retainft_lr1e-05] step 33: forget 0.305 retain +0.033 mia 1.000
[2026-10-25 07:01:55] [retainft_lr1e-05] step 36: forget 0.306 retain +0.031 mia 1.000
[2026-10-25 07:01:59] [retainft_lr1e-05] step 39: forget 0.308 retain +0.031 mia 1.000
[2026-10-25 07:02:03] [retainft_lr1e-05] step 42: forget 0.312 retain +0.032 mia 1.000
[2026-10-25 07:02:07] [retainft_lr1e-05] step 45: forget 0.315 retain +0.034 mia 1.000
[2026-10-25 07:02:11] [retainft_lr1e-05] step 48: forget 0.316 retain +0.034 mia 1.000
[2026-10-25 07:02:15] [retainft_lr1e-05] step 51: forget 0.313 retain +0.030 mia 1.000
[2026-10-25 07:02:18] [retainft_lr1e-05] step 54: forget 0.310 retain +0.025 mia 1.000
[2026-10-25 07:02:22] [retainft_lr1e-05] step 57: forget 0.310 retain +0.022 mia 1.000
[2026-10-25 07:02:26] [retainft_lr1e-05] step 60: forget 0.312 retain +0.021 mia 1.000
[2026-10-25 07:02:30] [retainft_lr1e-05] step 63: forget 0.314 retain +0.021 mia 1.000
[2026-10-25 07:02:34] [retainft_lr1e-05] step 66: forget 0.315 retain +0.021 mia 1.000
[2026-10-25 07:02:38] [retainft_lr1e-05] step 69: forget 0.316 retain +0.020 mia 1.000
[2026-10-25 07:02:42] [retainft_lr1e-05] step 72: forget 0.318 retain +0.020 mia 1.000
[2026-10-25 07:02:45] [retainft_lr1e-05] step 75: forget 0.320 retain +0.020 mia 1.000
[2026-10-25 07:02:49] [retainft_lr1e-05] step 78: forget 0.320 retain +0.020 mia 1.000
[2026-10-25 07:02:53] [retainft_lr1e-05] step 81: forget 0.322 retain +0.020 mia 1.000
[2026-10-25 07:02:57] [retainft_lr1e-05] step 84: forget 0.321 retain +0.019 mia 1.000
[2026-10-25 07:03:01] [retainft_lr1e-05] step 87: forget 0.321 retain +0.017 mia 1.000
[2026-10-25 07:03:05] [retainft_lr1e-05] step 90: forget 0.322 retain +0.017 mia 1.000
[2026-10-25 07:03:09] [retainft_lr1e-05] step 93: forget 0.324 retain +0.019 mia 1.000
[2026-10-25 07:03:13] [retainft_lr1e-05] step 96: forget 0.327 retain +0.019 mia 1.000
[2026-10-25 07:03:17] [retainft_lr1e-05] step 99: forget 0.329 retain +0.020 mia 1.000
[2026-10-25 07:03:21] [retainft_lr1e-05] step 102: forget 0.329 retain +0.019 mia 1.000
[2026-10-25 07:03:25] [retainft_lr1e-05] step 105: forget 0.331 retain +0.020 mia 1.000
[2026-10-25 07:03:29] [retainft_lr1e-05] step 108: forget 0.335 retain +0.020 mia 1.000
[2026-10-25 07:03:33] [retainft_lr1e-05] step 111: forget 0.336 retain +0.019 mia 1.000
[2026-10-25 07:03:37] [retainft_lr1e-05] step 114: forget 0.335 retain +0.018 mia 1.000
[2026-10-25 07:03:41] [retainft_lr1e-05] step 117: forget 0.334 retain +0.018 mia 1.000
[2026-10-25 07:03:45] [retainft_lr1e-05] step 120: forget 0.335 retain +0.017 mia 1.000
[2026-10-25 07:03:48] [retainft_lr1e-05] step 123: forget 0.333 retain +0.019 mia 1.000
[2026-10-25 07:03:52] [retainft_lr1e-05] step 126: forget 0.335 retain +0.020 mia 1.000
[2026-10-25 07:03:56] [retainft_lr1e-05] step 129: forget 0.335 retain +0.019 mia 1.000
[2026-10-25 07:04:00] [retainft_lr1e-05] step 132: forget 0.337 retain +0.016 mia 1.000
[2026-10-25 07:04:04] [retainft_lr1e-05] step 135: forget 0.339 retain +0.015 mia 1.000
[2026-10-25 07:04:08] [retainft_lr1e-05] step 138: forget 0.341 retain +0.015 mia 1.000
[2026-10-25 07:04:12] [retainft_lr1e-05] step 141: forget 0.342 retain +0.014 mia 1.000
[2026-10-25 07:04:16] [retainft_lr1e-05] step 144: forget 0.342 retain +0.012 mia 1.000
[2026-10-25 07:04:20] [retainft_lr1e-05] step 147: forget 0.341 retain +0.011 mia 1.000
[2026-10-25 07:04:24] [retainft_lr1e-05] step 150: forget 0.343 retain +0.009 mia 1.000
[2026-10-25 07:04:28] [retainft_lr1e-05] step 153: forget 0.345 retain +0.009 mia 1.000
[2026-10-25 07:04:32] [retainft_lr1e-05] step 156: forget 0.347 retain +0.011 mia 1.000
[2026-10-25 07:04:35] [retainft_lr1e-05] step 159: forget 0.348 retain +0.010 mia 1.000
[2026-10-25 07:04:39] [retainft_lr1e-05] step 162: forget 0.348 retain +0.009 mia 1.000
[2026-10-25 07:04:43] [retainft_lr1e-05] step 165: forget 0.348 retain +0.008 mia 1.000
[2026-10-25 07:04:47] [retainft_lr1e-05] step 168: forget 0.348 retain +0.008 mia 1.000
[2026-10-25 07:04:51] [retainft_lr1e-05] step 171: forget 0.346 retain +0.005 mia 1.000
[2026-10-25 07:04:55] [retainft_lr1e-05] step 174: forget 0.345 retain +0.001 mia 1.000
[2026-10-25 07:04:59] [retainft_lr1e-05] step 177: forget 0.347 retain +-0.002 mia 1.000
[2026-10-25 07:05:03] [retainft_lr1e-05] step 180: forget 0.347 retain +-0.005 mia 1.000
[2026-10-25 07:05:07] [retainft_lr1e-05] step 183: forget 0.348 retain +-0.004 mia 1.000
[2026-10-25 07:05:11] [retainft_lr1e-05] step 186: forget 0.349 retain +-0.003 mia 1.000
[2026-10-25 07:05:15] [retainft_lr1e-05] step 189: forget 0.350 retain +-0.002 mia 1.000
[2026-10-25 07:05:19] [retainft_lr1e-05] step 192: forget 0.350 retain +-0.001 mia 1.000
[2026-10-25 07:05:23] [retainft_lr1e-05] step 195: forget 0.352 retain +0.000 mia 1.000
[2026-10-25 07:05:27] [retainft_lr1e-05] step 198: forget 0.353 retain +-0.001 mia 1.000
[2026-10-25 07:05:31] [retainft_lr1e-05] step 201: forget 0.354 retain +-0.002 mia 1.000
[2026-10-25 07:05:35] [retainft_lr1e-05] step 204: forget 0.353 retain +-0.002 mia 1.000
[2026-10-25 07:05:39] [retainft_lr1e-05] step 207: forget 0.353 retain +-0.002 mia 1.000
[2026-10-25 07:05:43] [retainft_lr1e-05] step 210: forget 0.352 retain +-0.001 mia 1.000
[2026-10-25 07:05:47] [retainft_lr1e-05] step 213: forget 0.353 retain +0.001 mia 1.000
[2026-10-25 07:05:51] [retainft_lr1e-05] step 216: forget 0.353 retain +0.002 mia 1.000
[2026-10-25 07:05:55] [retainft_lr1e-05] step 219: forget 0.354 retain +0.003 mia 1.000
[2026-10-25 07:05:58] [retainft_lr1e-05] step 222: forget 0.354 retain +0.003 mia 1.000
[2026-10-25 07:06:02] [retainft_lr1e-05] step 225: forget 0.354 retain +0.002 mia 1.000
[2026-10-25 07:06:06] [retainft_lr1e-05] step 228: forget 0.355 retain +0.001 mia 1.000
[2026-10-25 07:06:10] [retainft_lr1e-05] step 231: forget 0.358 retain +0.001 mia 1.000
[2026-10-25 07:06:14] [retainft_lr1e-05] step 234: forget 0.360 retain +0.002 mia 1.000
[2026-10-25 07:06:18] [retainft_lr1e-05] step 237: forget 0.363 retain +0.003 mia 1.000
[2026-10-25 07:06:22] [retainft_lr1e-05] step 240: forget 0.363 retain +0.002 mia 1.000
[2026-10-25 07:06:26] [retainft_lr1e-05] finished: never_reached, op_step=None, promoted=True, 322s
[2026-10-25 07:06:26] STAGE 5: full evaluation battery
[2026-10-25 07:07:19] [eval oracle] {"name": "oracle", "forget_nll": 4.279312668740749, "holdout_nll": 4.506351673305034, "retain_nll": 0.3348911778070033, "mia_auc": 0.55115, "mink_auc": 0.564125, "forget_rouge": 0.2694049501945276, "retain_rouge": 0.49087731406580654, "model_utility": null, "forget_quality": null, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/oracle_final", "seconds": 50.99750518798828}
[2026-10-25 07:07:53] [eval target] {"name": "target", "forget_nll": 0.26313516072579657, "holdout_nll": 4.692464680671692, "retain_nll": 0.28390602122060954, "mia_auc": 0.998775, "mink_auc": 0.999, "forget_rouge": 0.6538872918956059, "retain_rouge": 0.5381845233032816, "ks_stat_nll": 0.99, "ks_p_nll": 1.550229472718744e-114, "model_utility": null, "forget_quality": 1.3850840057169374e-11, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/target_final", "seconds": 33.688135623931885}
[2026-10-25 07:08:26] [eval pretrained] {"name": "pretrained", "forget_nll": 2.809641990959644, "holdout_nll": 2.7942432737350464, "retain_nll": 2.8124940201640127, "mia_auc": 0.493375, "mink_auc": 0.5011000000000001, "forget_rouge": 0.23697529606527368, "retain_rouge": 0.19836051466991386, "ks_stat_nll": 0.565, "ks_p_nll": 8.970241343959439e-30, "model_utility": null, "forget_quality": 4.734741877153768e-15, "ckpt": "EleutherAI/pythia-160m", "seconds": 32.95496368408203}
[2026-10-25 07:09:02] [eval ga] {"name": "ga", "forget_nll": 4.862038111686706, "holdout_nll": 8.82781340122223, "retain_nll": 3.795659466981888, "mia_auc": 0.952325, "mink_auc": 0.916075, "forget_rouge": 0.20338699808272692, "retain_rouge": 0.2536670682158762, "ks_stat_nll": 0.205, "ks_p_nll": 0.0004306111484986726, "model_utility": null, "forget_quality": 6.5689645859369454e-12, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/v2/best_ga", "seconds": 35.65902280807495}
[2026-10-25 07:09:38] [eval graddiff] {"name": "graddiff", "forget_nll": 4.397162734866142, "holdout_nll": 6.678811581730843, "retain_nll": 1.2962857735157014, "mia_auc": 0.79955, "mink_auc": 0.6979500000000001, "forget_rouge": 0.26649984836288565, "retain_rouge": 0.30714313086712675, "ks_stat_nll": 0.085, "ks_p_nll": 0.46628639073563594, "model_utility": null, "forget_quality": 8.056669472003223e-07, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/v2/best_graddiff", "seconds": 35.55545783042908}
[2026-10-25 07:10:14] [eval npo] {"name": "npo", "forget_nll": 4.284772878885269, "holdout_nll": 8.105267231464387, "retain_nll": 3.479212149977684, "mia_auc": 0.9623999999999999, "mink_auc": 0.8862, "forget_rouge": 0.2399873489005296, "retain_rouge": 0.30491786248897806, "ks_stat_nll": 0.16, "ks_p_nll": 0.011843449760085422, "model_utility": null, "forget_quality": 1.3850840057169374e-11, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/v2/best_npo", "seconds": 35.40473175048828}
[2026-10-25 07:10:49] [eval npo_rt] {"name": "npo_rt", "forget_nll": 3.192691224813461, "holdout_nll": 4.8636926698684695, "retain_nll": 0.5076061319373548, "mia_auc": 0.815875, "mink_auc": 0.715025, "forget_rouge": 0.2676417020517891, "retain_rouge": 0.43402023703841097, "ks_stat_nll": 0.405, "ks_p_nll": 4.734741877153768e-15, "model_utility": null, "forget_quality": 2.3797467071606504e-06, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/v2/best_npo_rt", "seconds": 35.215275287628174}
[2026-10-25 07:11:25] [eval retainft] {"name": "retainft", "forget_nll": 0.3625380486249924, "holdout_nll": 4.806042931824923, "retain_nll": 0.28567923825234176, "mia_auc": 0.99735, "mink_auc": 0.997425, "forget_rouge": 0.5404944437029375, "retain_rouge": 0.5873911917912021, "ks_stat_nll": 0.985, "ks_p_nll": 2.0566377671402003e-112, "model_utility": null, "forget_quality": 2.8873674273022313e-11, "ckpt": "/content/drive/MyDrive/ssu_tf/ckpt/v2/best_retainft", "seconds": 35.27635383605957}
[2026-10-25 07:11:25] STAGE 6: relearning probe
[2026-10-25 07:11:37] [relearn oracle] {'pre_nll': 4.344039522608122, 'post_nll': 3.6872576723496118, 'post_rouge': 0.3071647212754054, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-25 07:11:48] [relearn ga] {'pre_nll': 4.838957317670187, 'post_nll': 0.7813439648546693, 'post_rouge': 0.3301719254246851, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-25 07:11:59] [relearn graddiff] {'pre_nll': 4.408129715588358, 'post_nll': 1.5441931530419324, 'post_rouge': 0.33900565610779515, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-25 07:12:10] [relearn npo] {'pre_nll': 4.2516943454742435, 'post_nll': 0.7637549886479974, 'post_rouge': 0.3543923498355079, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-25 07:12:21] [relearn npo_rt] {'pre_nll': 3.1821323732535043, 'post_nll': 1.840546187510093, 'post_rouge': 0.2753833334988532, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-25 07:12:32] [relearn retainft] {'pre_nll': 0.366807224891252, 'post_nll': 0.5030200515563289, 'post_rouge': 0.4274350190508301, 'n_relearn': 20, 'n_heldout': 180}
[2026-10-25 07:12:32] STAGE 7: report
[2026-10-25 07:12:33] report written: /content/drive/MyDrive/ssu_tf/report_v2.md
