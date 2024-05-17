#include <vector>
#include <gtest/gtest.h> 
std::vector<int> increaseAllByN(const std::vector<int>& vec, int n)
{
    std::vector<int> result;
    for (int num : vec) {
        result.push_back(num + n);
    }
    return result;
}
class IncreaseAllByNTest : public ::testing::Test {
protected:  
    virtual void SetUp() {  
        vector = {1, 2, 3};
    }    
    std::vector<int> vector;
};
TEST_F(IncreaseAllByNTest, IncreaseByOne) {
    auto result = increaseAllByN(vector, 1);
    ASSERT_THAT(result, ::testing::ElementsAre(2, 3, 4));
}
TEST_F(IncreaseAllByNTest, IncreaseByTwo) {
    auto result = increaseAllByN(vector, 2);
    ASSERT_THAT(result, ::testing::ElementsAre(3, 4, 5));
}
TEST_F(IncreaseAllByNTest, NoChange) {
    auto result = increaseAllByN(vector, 0);
    ASSERT_THAT(result, ::testing::ElementsAre(1, 2, 3));
}
int main(int argc, char  *  * argv) {
    ::testing::InitGoogleTest(&argc, argv);
    return RUN_ALL_TESTS();
}
