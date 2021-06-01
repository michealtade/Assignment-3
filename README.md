# Assignment-3
frequency_cesearcipher
package micheal;

public class frequency_cesearcipher {
	public static String decode1 (String code){
	    var key=0;
	    final int ALPHABET_SIZE = 26;
	    int[] freqs = new int[ALPHABET_SIZE];
	    for (int l=0;l<freqs.length;l++){ 
	        freqs[l]=0;	    
	    }
	    for (int k=0;k<code.length();k++){
	        if (code.charAt(k)>='a' && code.charAt(k)<='z'){
	            freqs[code.charAt(k)-'a']++;
	        }
	    }
	    int biggest = 0;
	    for (int t=0;t<freqs.length;t++){
	        if (freqs[t]>biggest){
	            biggest= t;
	        }
	    }
	    if (biggest<4){
	        key = (biggest + 26 - ('e'+'a'));

	    }
	    else{
	        key = biggest + 'a' - 'e';
	    }
	    return (decode1(code));
	}
	public static String decode (String code){
	    int key = 0;
	    final int ALPHABET_SIZE = 26;
	    int[] freqs = new int[ALPHABET_SIZE];

	    int highestFreq = 0;
	    int highestFreqIdx = -1;
	    for (int k=0; k < code.length(); k++) {
	        if (code.charAt(k) >= 'a' && code.charAt(k) <= 'z') {
	            int count = freqs[code.charAt(k)-'a']++;

	            if (count > highestFreq) {
	              highestFreq = count;
	              highestFreqIdx = k;
	            }
	        }
	    }

	    key = highestFreqIdx - ('e' - 'a'); // Can also directly use 4 instead of 'e' - 'a'

	    return (decode1(code));
	}

}
