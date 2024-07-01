- int b[8]; 
 
inline static int unsafe(int y) { 
        int i, t, x; 
        x = b[y]; 
        for (i = 1; i <= y; i++) { 
                t = b[y - i]; 
                if ((t == x) || 
                     (t == x - i) || 
                     (t == x + i)) { 
                        return 1; 
               } 
       } 
 
        return 0; 
} 
 
static void putboard(void) { 
        static int s = ۰; 
        int x, y; 
        printf("\n\nSolution #٪i\n", ++s); 
        for (y = 0; y < 8; y++) { 
                for (x = 0; x < 8; x++) { 
                        printf((b[y] == x) ? "|Q": "|_"); 
               } 
                printf("|\n"); 
       } 
} 
 
int main(void) { 
        int y = ۰; 
        b[۰] = -۱; 
        while (y >= ۰) { 
                do { 
                        b[y]++; 
               } while ((b[y] < 8) && unsafe(y)); 
                if (b[y] < 8) { 
                        if (y < 7) { 
                                b[++y] = -۱; 
                       } else { 
                                putboard(); 
                       } 
               } else { 
                        y--; 
               } 
       } 
 
        return 0; 
}
