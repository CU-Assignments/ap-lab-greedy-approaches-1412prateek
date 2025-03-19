class Solution {
    public int maxTaskAssign(int[] tasks, int[] workers, int pills, int strength) {
        int left = 0, right = Math.min(tasks.length, workers.length);
        Arrays.sort(tasks);
        Arrays.sort(workers);
        while(left+1<right)
        {
            int mid = left + (right - left)/2;
            if(canAssign(mid, tasks, workers, pills, strength))
            {
                left = mid;
            }
            else
            {
                right = mid;
            }
        }
        
        if(canAssign(right, tasks, workers, pills, strength))
        {
            return right;
        }
        else return left;
    }
    
      public boolean canAssign(int count, int[] tasks, int[] workers, int pills, int strength){
        Deque<Integer> dq = new ArrayDeque<>();
        int ind = workers.length - 1;
        for (int i = count - 1; i >= 0; i--) {
            while(ind>=workers.length-count && workers[ind]+strength>=tasks[i])
            {
              dq.offerLast(workers[ind]);
              ind--;
            }
            
            if(dq.isEmpty())return false;
            if(dq.peekFirst()>=tasks[i])
            {
                dq.pollFirst();
            }
            else
            {
                dq.pollLast();
                pills--;
                if(pills<0)return false;
            }
        }
          
        return true;
    }
}
