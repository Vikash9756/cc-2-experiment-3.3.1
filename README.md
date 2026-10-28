# cc-2-experiment-3.3.1
--Number of Islands--

class Solution {
public:
int numIslands(vector<vector<char>>& grid) {
if (grid.empty() || grid[0].empty()) {
return 0;
}

    int m = grid.size();
    int n = grid[0].size();
    int count = 0;

    for (int r = 0; r < m; r++) {
        for (int c = 0; c < n; c++) {
            if (grid[r][c] == '1') {
                dfs(grid, r, c, m, n);
                count++;
            }
        }
    }

    return count;
}


private:
void dfs(vector<vector<char>>& grid, int r, int c, int m, int n) {
if (r < 0 || r >= m || c < 0 || c >= n ||
grid[r][c] != '1') {
return;
}

    grid[r][c] = '0';

    dfs(grid, r - 1, c, m, n);
    dfs(grid, r + 1, c, m, n);
    dfs(grid, r, c - 1, m, n);
    dfs(grid, r, c + 1, m, n);
}


};
