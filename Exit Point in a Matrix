class Solution {
  public:
    int check(int i,int j,int n,int m){
        if(i<0 or i>=n) return 1;
        if(j<0 or j>=m) return 1;
        return 0;
    }
    vector<int> FindExitPoint(int n, int m, vector<vector<int>>& matrix) {
        vector<int> dx={0,1,0,-1};
        vector<int> dy={1,0,-1,0};
        int x=0,y=0;
        int c=0;
        while(true){
            if(matrix[x][y]==1){
                matrix[x][y]=0;
                c++;
                c%=4;
            }
            x+=dx[c];
            y+=dy[c];
            if(check(x,y,n,m)) return {x-dx[c],y-dy[c]};
        }
    }
};
