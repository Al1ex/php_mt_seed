# php_mt_seed
php_mt_seed is a PHP mt_rand() seed cracker. In the most trivial invocation mode, it finds possible seeds given the very first mt_rand() output after possible seeding with mt_srand(). With advanced invocation modes, it is also able to match multiple, non-first, and/or inexact mt_rand() outputs to possible seed values.

PHP's mt_rand() algorithm changed over the years since its introduction in PHP 3.0.6. php_mt_seed 4.0 supports 3 major revisions of the algorithm: PHP 3.0.7 to 5.2.0, PHP 5.2.1 to 7.0.x, and PHP 7.1.0+ (at least up to the latest as of this writing, which is PHP 7.2.0beta3).

php_mt_seed uses attack-optimized reimplementations of PHP's mt_rand() algorithms. It is written in C with optional SIMD intrinsics (SSE2, SSE4.1/AVX, XOP, AVX2, AVX-512, as well as MIC) and OpenMP. On a modern quad-core CPU, it is able to search the full 32-bit seed space in under a minute. On second generation Xeon Phi, it does the same in 3 seconds.
