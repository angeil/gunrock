
# Scalability on multiple GPUs

Scalability of DOBFS, BFS, and PR. {Strong, weak edge, weak vertex} scaling use rmat graphs with {2<sup>24</sup>, 2<sup>19</sup>, 2<sup>19</sup>&nbsp;&times;&nbsp;|GPUs|} vertices and edge factor {32, 256&nbsp;&times;&nbsp;|GPUs|, 256} respectively. DOBFS runs have idempotence disabled, though results with idempotence enabled have similar runtimes.

While providing both weak-vertex and -edge scaling, DOBFS doesn't have good strong scaling, because its computation and communication are both roughly on the order of O(|V<sub>i</sub>|). This effect is more obvious on P100, as computation is faster but inter-GPU bandwidth stays mostly the same. BFS and PR achieve almost linear weak and strong scaling from 1 to 8 GPUs.

DOBFS
\htmlonly

  <!-- Container for the visualization mgpu_scalability_DOBFS -->
  <div id="vis_mgpu_scalability_DOBFS"></div>
  <script>
  var vlSpec = {
    "mark": "point", 
    "data": {
        "values": [
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1048576_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1048576_e256_Fri Jan 27 074529 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:45:29 2017\n", 
                "elapsed": 1.7270445823669434, 
                "m_teps": 232757.25, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1048576_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1048576_e256_Fri Jan 27 101817 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:18:17 2017\n", 
                "elapsed": 1.0460615158081055, 
                "m_teps": 384277.40625, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1572864_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1572864_e256_Fri Jan 27 074605 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:46:05 2017\n", 
                "elapsed": 2.6033968925476074, 
                "m_teps": 219112.640625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1572864_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1572864_e256_Fri Jan 27 101850 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:18:50 2017\n", 
                "elapsed": 1.2840330600738525, 
                "m_teps": 444279.65625, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_2097152_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_2097152_e256_Fri Jan 27 074654 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:46:54 2017\n", 
                "elapsed": 3.5712270736694336, 
                "m_teps": 235041.25, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_2097152_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_2097152_e256_Fri Jan 27 101932 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:19:32 2017\n", 
                "elapsed": 2.255558967590332, 
                "m_teps": 372100.1875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 5, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_2621440_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_2621440_e256_Fri Jan 27 074754 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:47:54 2017\n", 
                "elapsed": 4.527971267700195, 
                "m_teps": 225779.4375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 6, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_3145728_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_3145728_e256_Fri Jan 27 074907 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:49:07 2017\n", 
                "elapsed": 5.3407697677612305, 
                "m_teps": 224567.203125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 7, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_3670016_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_3670016_e256_Fri Jan 27 075035 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:50:35 2017\n", 
                "elapsed": 5.7004241943359375, 
                "m_teps": 240574.78125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 8, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_4194304_e255", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_4194304_e255_Fri Jan 27 075217 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:52:17 2017\n", 
                "elapsed": 9.38868522644043, 
                "m_teps": 184865.59375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_524288_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_524288_e256_Fri Jan 27 074507 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:45:07 2017\n", 
                "elapsed": 0.720679759979248, 
                "m_teps": 265592.09375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_524288_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_524288_e256_Fri Jan 27 101757 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:17:57 2017\n", 
                "elapsed": 0.2704709768295288, 
                "m_teps": 707654.5625, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1024", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1024_Fri Jan 27 081856 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:18:56 2017\n", 
                "elapsed": 1.7760992050170898, 
                "m_teps": 335792.4375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1024", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1024_Fri Jan 27 103007 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:30:07 2017\n", 
                "elapsed": 1.2266933917999268, 
                "m_teps": 486193.65625, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 5, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1280", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1280_Fri Jan 27 081953 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:19:53 2017\n", 
                "elapsed": 2.1333694458007812, 
                "m_teps": 332780.25, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 6, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1536", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1536_Fri Jan 27 082102 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:21:02 2017\n", 
                "elapsed": 2.570554733276367, 
                "m_teps": 317853.625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 7, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1792", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1792_Fri Jan 27 082219 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:22:19 2017\n", 
                "elapsed": 2.750441551208496, 
                "m_teps": 334030.65625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 8, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e2047", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e2047_Fri Jan 27 082348 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:23:48 2017\n", 
                "elapsed": 4.502773284912109, 
                "m_teps": 225591.390625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e256_Fri Jan 27 081712 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:17:12 2017\n", 
                "elapsed": 0.7514059543609619, 
                "m_teps": 254722.90625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e256_Fri Jan 27 102837 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:28:37 2017\n", 
                "elapsed": 0.2724379301071167, 
                "m_teps": 702562.75, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e512", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e512_Fri Jan 27 081736 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:17:36 2017\n", 
                "elapsed": 1.1787563562393188, 
                "m_teps": 289832.0, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e512", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e512_Fri Jan 27 102857 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:28:57 2017\n", 
                "elapsed": 0.815272331237793, 
                "m_teps": 418998.15625, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e768", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e768_Fri Jan 27 081811 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:18:11 2017\n", 
                "elapsed": 1.7042160034179688, 
                "m_teps": 278498.6875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e768", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e768_Fri Jan 27 102927 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:29:27 2017\n", 
                "elapsed": 0.9507685899734497, 
                "m_teps": 499200.6875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065040 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:50:40 2017\n", 
                "elapsed": 18.687978744506836, 
                "m_teps": 54643.2265625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065126 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:51:26 2017\n", 
                "elapsed": 16.4417781829834, 
                "m_teps": 62265.36328125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065230 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:52:30 2017\n", 
                "elapsed": 17.38521385192871, 
                "m_teps": 58887.09765625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065335 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:53:35 2017\n", 
                "elapsed": 18.63141441345215, 
                "m_teps": 54947.5703125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 5, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065442 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:54:42 2017\n", 
                "elapsed": 20.40824317932129, 
                "m_teps": 50163.37890625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 6, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065548 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:55:48 2017\n", 
                "elapsed": 22.293254852294922, 
                "m_teps": 45921.55078125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 7, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065657 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:56:57 2017\n", 
                "elapsed": 22.864952087402344, 
                "m_teps": 44773.15625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 8, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 065807 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:58:07 2017\n", 
                "elapsed": 23.934661865234375, 
                "m_teps": 42773.48828125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 100059 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:00:59 2017\n", 
                "elapsed": 4.194169998168945, 
                "m_teps": 243476.78125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 100143 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:01:43 2017\n", 
                "elapsed": 6.268307685852051, 
                "m_teps": 163320.953125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 100242 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:02:42 2017\n", 
                "elapsed": 8.154884338378906, 
                "m_teps": 125537.53125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "DOBFS", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 100340 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:03:40 2017\n", 
                "elapsed": 10.199605941772461, 
                "m_teps": 100371.578125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": true, 
                "gunrock_version": "0.4.0"
            }
        ]
    }, 
    "encoding": {
        "y": {
            "field": "m_teps", 
            "type": "quantitative", 
            "axis": {
                "title": "MTEPS"
            }
        }, 
        "color": {
            "field": "[gpuinfo.name]", 
            "type": "nominal", 
            "legend": {
                "title": "GPU"
            }
        }, 
        "shape": {
            "field": "scalability", 
            "type": "nominal", 
            "legend": {
                "title": "Scalability Type"
            }
        }, 
        "x": {
            "field": "num_gpus", 
            "type": "nominal", 
            "axis": {
                "title": "Number of GPUs"
            }
        }
    }
}
  var embedSpec = {
    mode: "vega-lite",  // Instruct Vega-Embed to use the Vega-Lite compiler
    spec: vlSpec
  };
  // Embed the visualization in the container with id `vis_mgpu_scalability_DOBFS`
  vg.embed("#vis_mgpu_scalability_DOBFS", embedSpec, function(error, result) {
    // Callback receiving the View instance and parsed Vega spec
    // result.view is the View, which resides under the
    // '#vis_mgpu_scalability_DOBFS' element
  });
  </script>

\endhtmlonly

BFS
\htmlonly

  <!-- Container for the visualization mgpu_scalability_BFS -->
  <div id="vis_mgpu_scalability_BFS"></div>
  <script>
  var vlSpec = {
    "mark": "point", 
    "data": {
        "values": [
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 2, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_1048576_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1048576_e256_Fri Jan 27 073737 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:37:37 2017\n", 
                "elapsed": 37.249237060546875, 
                "m_teps": 10792.455078125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 2, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_1048576_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1048576_e256_Fri Jan 27 101532 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:15:32 2017\n", 
                "elapsed": 7.979541778564453, 
                "m_teps": 50378.2421875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 3, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_1572864_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1572864_e256_Fri Jan 27 073816 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:38:16 2017\n", 
                "elapsed": 36.07904815673828, 
                "m_teps": 15811.5517578125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 3, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_1572864_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_1572864_e256_Fri Jan 27 101605 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:16:05 2017\n", 
                "elapsed": 8.223518371582031, 
                "m_teps": 69367.4296875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 4, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_2097152_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_2097152_e256_Fri Jan 27 073906 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:39:06 2017\n", 
                "elapsed": 43.80760955810547, 
                "m_teps": 19159.458984375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 4, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_2097152_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_2097152_e256_Fri Jan 27 101648 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:16:48 2017\n", 
                "elapsed": 10.368794441223145, 
                "m_teps": 80948.1328125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 5, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_2621440_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_2621440_e256_Fri Jan 27 074009 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:40:09 2017\n", 
                "elapsed": 43.02737045288086, 
                "m_teps": 23759.70703125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 6, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_3145728_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_3145728_e256_Fri Jan 27 074123 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:41:23 2017\n", 
                "elapsed": 42.345462799072266, 
                "m_teps": 28322.3125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 7, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_3670016_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_3670016_e256_Fri Jan 27 074248 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:42:48 2017\n", 
                "elapsed": 41.956947326660156, 
                "m_teps": 32685.29296875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 8, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_4194304_e255", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_4194304_e255_Fri Jan 27 074426 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:44:26 2017\n", 
                "elapsed": 53.253173828125, 
                "m_teps": 32592.580078125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 1, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_524288_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_524288_e256_Fri Jan 27 073715 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:37:15 2017\n", 
                "elapsed": 32.81468200683594, 
                "m_teps": 5833.03076171875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 1, 
                "idempotent": true, 
                "scalability": "weak edge", 
                "dataset": "rmat_524288_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_524288_e256_Fri Jan 27 101513 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:15:13 2017\n", 
                "elapsed": 6.734833240509033, 
                "m_teps": 28421.48828125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 4, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1024", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1024_Fri Jan 27 081146 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:11:46 2017\n", 
                "elapsed": 25.899991989135742, 
                "m_teps": 23027.29296875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 4, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1024", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1024_Fri Jan 27 102732 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:27:32 2017\n", 
                "elapsed": 6.203621864318848, 
                "m_teps": 96137.609375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 5, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1280", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1280_Fri Jan 27 081244 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:12:44 2017\n", 
                "elapsed": 24.8474178314209, 
                "m_teps": 28572.369140625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 6, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1536", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1536_Fri Jan 27 081352 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:13:52 2017\n", 
                "elapsed": 24.222105026245117, 
                "m_teps": 33727.80078125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 7, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1792", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e1792_Fri Jan 27 081511 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:15:11 2017\n", 
                "elapsed": 23.62437629699707, 
                "m_teps": 38893.10546875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 8, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e2047", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e2047_Fri Jan 27 081642 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:16:42 2017\n", 
                "elapsed": 23.092226028442383, 
                "m_teps": 43986.68359375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 1, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e256_Fri Jan 27 080957 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:09:57 2017\n", 
                "elapsed": 32.760738372802734, 
                "m_teps": 5842.9482421875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 1, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e256_Fri Jan 27 102602 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:26:02 2017\n", 
                "elapsed": 6.655707836151123, 
                "m_teps": 28755.55078125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 2, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e512", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e512_Fri Jan 27 081021 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:10:21 2017\n", 
                "elapsed": 29.382095336914062, 
                "m_teps": 11626.529296875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 2, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e512", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e512_Fri Jan 27 102621 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:26:21 2017\n", 
                "elapsed": 6.268277645111084, 
                "m_teps": 54491.3046875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 3, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e768", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e768_Fri Jan 27 081058 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:10:58 2017\n", 
                "elapsed": 27.43855094909668, 
                "m_teps": 17298.140625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 3, 
                "idempotent": true, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e768", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n19_e768_Fri Jan 27 102652 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:26:52 2017\n", 
                "elapsed": 6.4462127685546875, 
                "m_teps": 73631.8203125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 1, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064111 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:41:11 2017\n", 
                "elapsed": 256.11761474609375, 
                "m_teps": 3987.1240234375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 2, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064203 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:42:03 2017\n", 
                "elapsed": 146.9174346923828, 
                "m_teps": 6968.1806640625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 3, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064312 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:43:12 2017\n", 
                "elapsed": 108.34002685546875, 
                "m_teps": 9449.509765625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 4, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064415 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:44:15 2017\n", 
                "elapsed": 87.58155822753906, 
                "m_teps": 11689.20703125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 5, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064521 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:45:21 2017\n", 
                "elapsed": 76.31367492675781, 
                "m_teps": 13415.1103515625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 6, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064625 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:46:25 2017\n", 
                "elapsed": 67.68612670898438, 
                "m_teps": 15124.8720703125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 7, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064734 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:47:34 2017\n", 
                "elapsed": 62.48208999633789, 
                "m_teps": 16384.642578125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 8, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 064845 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 06:48:45 2017\n", 
                "elapsed": 57.707786560058594, 
                "m_teps": 17740.228515625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 1, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 095553 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 09:55:53 2017\n", 
                "elapsed": 55.023475646972656, 
                "m_teps": 18559.26953125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 2, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 095636 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 09:56:36 2017\n", 
                "elapsed": 34.66163635253906, 
                "m_teps": 29535.423828125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 3, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 095737 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 09:57:37 2017\n", 
                "elapsed": 27.018203735351562, 
                "m_teps": 37891.12109375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "BFS", 
                "num_gpus": 4, 
                "idempotent": true, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/BFS_rmat_n24_e32_Fri Jan 27 095834 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 09:58:34 2017\n", 
                "elapsed": 24.13834571838379, 
                "m_teps": 42411.95703125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }
        ]
    }, 
    "encoding": {
        "y": {
            "field": "m_teps", 
            "type": "quantitative", 
            "axis": {
                "title": "MTEPS"
            }
        }, 
        "color": {
            "field": "[gpuinfo.name]", 
            "type": "nominal", 
            "legend": {
                "title": "GPU"
            }
        }, 
        "shape": {
            "field": "scalability", 
            "type": "nominal", 
            "legend": {
                "title": "Scalability Type"
            }
        }, 
        "x": {
            "field": "num_gpus", 
            "type": "nominal", 
            "axis": {
                "title": "Number of GPUs"
            }
        }
    }
}
  var embedSpec = {
    mode: "vega-lite",  // Instruct Vega-Embed to use the Vega-Lite compiler
    spec: vlSpec
  };
  // Embed the visualization in the container with id `vis_mgpu_scalability_BFS`
  vg.embed("#vis_mgpu_scalability_BFS", embedSpec, function(error, result) {
    // Callback receiving the View instance and parsed Vega spec
    // result.view is the View, which resides under the
    // '#vis_mgpu_scalability_BFS' element
  });
  </script>

\endhtmlonly

PageRank
\htmlonly

  <!-- Container for the visualization mgpu_scalability_PageRank -->
  <div id="vis_mgpu_scalability_PageRank"></div>
  <script>
  var vlSpec = {
    "mark": "point", 
    "data": {
        "values": [
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1048576_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_1048576_e256_Fri Jan 27 075327 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:53:27 2017\n", 
                "elapsed": 792.2881841659546, 
                "m_teps": 507.3777160644531, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1048576_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_1048576_e256_Fri Jan 27 102103 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:21:03 2017\n", 
                "elapsed": 165.92945158481598, 
                "m_teps": 2422.6826171875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1572864_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_1572864_e256_Fri Jan 27 075413 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:54:13 2017\n", 
                "elapsed": 1246.0083365440369, 
                "m_teps": 457.8467102050781, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_1572864_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_1572864_e256_Fri Jan 27 102136 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:21:36 2017\n", 
                "elapsed": 176.59565806388855, 
                "m_teps": 3230.603271484375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_2097152_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_2097152_e256_Fri Jan 27 075519 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:55:19 2017\n", 
                "elapsed": 1289.7167652845383, 
                "m_teps": 650.82177734375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_2097152_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_2097152_e256_Fri Jan 27 102218 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:22:18 2017\n", 
                "elapsed": 233.281210064888, 
                "m_teps": 3597.844482421875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 5, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_2621440_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_2621440_e256_Fri Jan 27 075636 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:56:36 2017\n", 
                "elapsed": 1434.512808918953, 
                "m_teps": 712.6528930664062, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 6, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_3145728_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_3145728_e256_Fri Jan 27 075804 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:58:04 2017\n", 
                "elapsed": 1891.6661888360977, 
                "m_teps": 634.0078125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 7, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_3670016_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_3670016_e256_Fri Jan 27 075949 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:59:49 2017\n", 
                "elapsed": 1550.4877120256424, 
                "m_teps": 884.4547119140625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 8, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_4194304_e255", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_4194304_e255_Fri Jan 27 080146 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:01:46 2017\n", 
                "elapsed": 1786.0632836818695, 
                "m_teps": 971.7525024414062, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_524288_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_524288_e256_Fri Jan 27 075256 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:52:56 2017\n", 
                "elapsed": 542.1207249164581, 
                "m_teps": 353.07623291015625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak edge", 
                "dataset": "rmat_524288_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_524288_e256_Fri Jan 27 102044 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:20:44 2017\n", 
                "elapsed": 136.75588369369507, 
                "m_teps": 1399.6165771484375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1024", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e1024_Fri Jan 27 082619 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:26:19 2017\n", 
                "elapsed": 276.5166163444519, 
                "m_teps": 2156.812255859375, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1024", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e1024_Fri Jan 27 103242 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:32:42 2017\n", 
                "elapsed": 74.00742173194885, 
                "m_teps": 8059.23779296875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 5, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1280", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e1280_Fri Jan 27 082718 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:27:18 2017\n", 
                "elapsed": 260.5196535587311, 
                "m_teps": 2725.031982421875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 6, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1536", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e1536_Fri Jan 27 082825 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:28:25 2017\n", 
                "elapsed": 248.0381280183792, 
                "m_teps": 3293.975341796875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 7, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e1792", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e1792_Fri Jan 27 082940 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:29:40 2017\n", 
                "elapsed": 237.92289197444916, 
                "m_teps": 3861.7294921875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 8, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e2047", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e2047_Fri Jan 27 083110 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:31:10 2017\n", 
                "elapsed": 231.20611906051636, 
                "m_teps": 4393.0810546875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e256_Fri Jan 27 082417 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:24:17 2017\n", 
                "elapsed": 546.4855134487152, 
                "m_teps": 350.2718811035156, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e256", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e256_Fri Jan 27 103112 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:31:12 2017\n", 
                "elapsed": 136.51326298713684, 
                "m_teps": 1402.290283203125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e512", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e512_Fri Jan 27 082448 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:24:48 2017\n", 
                "elapsed": 348.9924818277359, 
                "m_teps": 978.80029296875, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e512", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e512_Fri Jan 27 103132 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:31:32 2017\n", 
                "elapsed": 96.37750685214996, 
                "m_teps": 3544.218505859375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e768", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e768_Fri Jan 27 082527 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 08:25:27 2017\n", 
                "elapsed": 439.1220360994339, 
                "m_teps": 1080.9102783203125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "weak vertex", 
                "dataset": "rmat_n19_e768", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n19_e768_Fri Jan 27 103203 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:32:03 2017\n", 
                "elapsed": 105.45146465301514, 
                "m_teps": 4500.98193359375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 070000 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:00:00 2017\n", 
                "elapsed": 28104.15467619896, 
                "m_teps": 36.33613586425781, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 070808 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:08:08 2017\n", 
                "elapsed": 14616.275936365128, 
                "m_teps": 70.04146575927734, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 071257 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:12:57 2017\n", 
                "elapsed": 9736.836239695549, 
                "m_teps": 105.14103698730469, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 071628 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:16:28 2017\n", 
                "elapsed": 7580.44208586216, 
                "m_teps": 135.05130004882812, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 5, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 071923 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:19:23 2017\n", 
                "elapsed": 6201.4816999435425, 
                "m_teps": 165.0824432373047, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 6, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 072158 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:21:58 2017\n", 
                "elapsed": 5289.211466908455, 
                "m_teps": 193.55548095703125, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 7, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 072422 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:24:22 2017\n", 
                "elapsed": 8434.645131230354, 
                "m_teps": 121.37269592285156, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 8, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 072739 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 07:27:39 2017\n", 
                "elapsed": 4768.329784274101, 
                "m_teps": 214.7017822265625, 
                "gpuinfo.name": "Tesla K80", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 1, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 100604 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:06:04 2017\n", 
                "elapsed": 5640.230506658554, 
                "m_teps": 181.05625915527344, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 2, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 100808 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:08:08 2017\n", 
                "elapsed": 2919.465512037277, 
                "m_teps": 350.66595458984375, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 3, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 100941 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:09:41 2017\n", 
                "elapsed": 2044.4184988737106, 
                "m_teps": 500.75811767578125, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }, 
            {
                "engine": "Gunrock", 
                "algorithm": "PageRank", 
                "num_gpus": 4, 
                "idempotent": false, 
                "scalability": "strong", 
                "dataset": "rmat_n24_e32", 
                "details": "<a href=\"https://github.com/gunrock/io/tree/master/gunrock-output/ipdps17/eval_fig5/PageRank_rmat_n24_e32_Fri Jan 27 101101 2017.json\">JSON output</a>", 
                "time": "Fri Jan 27 10:11:01 2017\n", 
                "elapsed": 1630.2269399166107, 
                "m_teps": 627.9705810546875, 
                "gpuinfo.name": "Tesla P100-PCIE-16GB", 
                "direction_optimized": false, 
                "gunrock_version": "0.4.0"
            }
        ]
    }, 
    "encoding": {
        "y": {
            "field": "m_teps", 
            "type": "quantitative", 
            "axis": {
                "title": "MTEPS"
            }
        }, 
        "color": {
            "field": "[gpuinfo.name]", 
            "type": "nominal", 
            "legend": {
                "title": "GPU"
            }
        }, 
        "shape": {
            "field": "scalability", 
            "type": "nominal", 
            "legend": {
                "title": "Scalability Type"
            }
        }, 
        "x": {
            "field": "num_gpus", 
            "type": "nominal", 
            "axis": {
                "title": "Number of GPUs"
            }
        }
    }
}
  var embedSpec = {
    mode: "vega-lite",  // Instruct Vega-Embed to use the Vega-Lite compiler
    spec: vlSpec
  };
  // Embed the visualization in the container with id `vis_mgpu_scalability_PageRank`
  vg.embed("#vis_mgpu_scalability_PageRank", embedSpec, function(error, result) {
    // Callback receiving the View instance and parsed Vega spec
    // result.view is the View, which resides under the
    // '#vis_mgpu_scalability_PageRank' element
  });
  </script>

\endhtmlonly


[[DOBFS source data](md_stats_mgpu_scalability__d_o_b_f_s_table_html.html)] [[BFS source data](md_stats_mgpu_scalability__b_f_s_table_html.html)] [[PageRank source data](md_stats_mgpu_scalability__page_rank_table_html.html)], with links to the output JSON for each run<br/>