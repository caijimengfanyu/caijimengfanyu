## 繁凡さん 
大二蒟蒻ACMer一只

我的博客：https://fanfansann.blog.csdn.net/ ！
来我的博客找我玩！

	void transform(int limit, int *A, int type) {
	    for (int i = 0; i < limit; i ++)
	        if (i < RR[i])
	            swap(A[i], A[RR[i]]); 
	    for (int mid = 1; mid < limit; mid <<= 1) {
	        int wn = qpow(root, (mod - 1) / (mid << 1)); 
	        for (int pos = 0; pos < limit; pos += (mid << 1)) {
	            int w = 1; 
	            for (int k = 0; k < mid; k ++, w = 1ll * w * wn % mod) {
	                int x = A[pos + k], y = 1ll * w * A[pos + mid + k] % mod;
	                A[pos + k] = (x + y) % mod;
	                A[pos + k + mid] = (1ll * x - y + mod) % mod;
	            }
	        }
	    } 
	    if (type == 1)
	        return ; 
	    for (int i = 1; i < limit / 2; i ++)
	        swap(A[i], A[limit - i]); 
	    int inv = qpow(limit, mod - 2); 
	    for (int i = 0; i < limit; i ++) {
	        A[i] = 1ll * A[i] * inv % mod;
	    }
	}
