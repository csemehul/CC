class Solution
{
public:
    int findShortestPath(vector<vector<int>> &mat)
    {
        int n = mat.size(), m = mat[0].size();
        vector<vector<int>> vis(n, vector<int>(m));
        int dx[4] = {-1, 1, 0, 0}, dy[4] = {0, 0, -1, 1};

        for (int i = 0; i < n; i++)
        {
            for (int j = 0; j < m; j++)
            {
                if (mat[i][j] == 0)
                {
                    for (int k = 0; k < 4; k++)
                    {
                        int nx = i + dx[k];
                        int ny = j + dy[k];
                        if (nx >= 0 and ny >= 0 and nx < n and ny < m and mat[nx][ny] == 1)
                            mat[nx][ny] = -1;
                    }
                }
            }
        }

        queue<pair<int, pair<int, int>>> q;
        for (int i = 0; i < n; i++)
        {
            if (mat[i][0] == 1)
            {
                q.push({0, {i, 0}});
                vis[i][0] = 1;
            }
        }

        int ans = INT_MAX;
        while (!q.empty())
        {
            int dist = q.front().first;
            int r = q.front().second.first;
            int c = q.front().second.second;
            q.pop();

            if (c == m - 1)
                ans = min(ans, dist + 1);

            for (int k = 0; k < 4; k++)
            {
                int nx = r + dx[k];
                int ny = c + dy[k];

                if (nx >= 0 and ny >= 0 and nx < n and ny < m and mat[nx][ny] == 1 and !vis[nx][ny])
                {
                    vis[nx][ny] = 1;
                    q.push({dist + 1, {nx, ny}});
                }
            }
        }

        return ans == INT_MAX ? -1 : ans;
    }
};
