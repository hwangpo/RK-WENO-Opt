# Script 

(just change p and s)

    x = load('Eigenvalues_CRWENO5.txt');
    z = x(:,1) + 1i*x(:,2);
    p = 4;
    s = 5;
    [h, poly_coeff] = opt_poly_bisect(z,s,p,'chebyshev','do_plot',true)
    rk = rk_opt(s,p,'erk','ssp','poly_coeff_ind',((p+1):s),'poly_coeff_val',poly_coeff((p+2):s+1),'display','iter')
    plot(real(h*z),imag(h*z),'o')
    hold on
    plotstabreg_func(poly_coeff,[1])

# Results

Values of h/s

## WENO5

### p = 3

s   | h/s   
--- | ------
3   | 0.4783
4   | 0.4694
5   | *0.5314*
6   | 0.5197
7   | 0.5389
8   | 0.5329
9   | 0.5384
10  | 0.5379
11  | 0.5395
12  | 0.5401


### p = 4

s   | h/s   
--- | ------
4   | 0.4330
5   | 0.3942
6   | 0.4892
7   | 0.4753
8   | 0.5041
9   | 0.5034
10  | 0.5154


### p = 5

s   | h/s   
--- | ------
5   | 0.3470
6   | 0.3293
7   | 0.3583
8   | 0.3896
9   | 0.3976
10  | 0.4104
11  | 0.4207
12  | 0.4260
13  | 0.4339
14  | 0.4376


## CRWENO5

### p = 3

s   | h/s   
--- | ------
3   | 0.2963
4   | 0.3057
5   | 0.3222
6   | 0.3275
7   | 0.3323
8   | 0.3356
9   | 0.3382
10  | 0.3400

### p = 4

s   | h/s   
--- | ------
4   | 0.2585
5   | 0.2586
6   | 0.2758
7   | 0.2888
8   | 0.2983
9   | 0.3064
10  | 0.3130


### p = 5

s   | h/s   
--- | ------
6   | 0.2366
7   | 0.2434
8   | 0.2501
9   | 0.2561
10  | 0.2609
11  | 0.2652
12  | 0.2691
13  | 0.2724
14  | 0.2756