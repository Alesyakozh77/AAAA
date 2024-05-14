#include <vector>
std::vector<int> increaseVector(std::vector<int> vec, int num) 
{
  for (int i = 0; i &lt; vec.size(); i++) {
 
  vec[i] += num;
    }
    return vec;
}
#define CATCH_CONFIG_MAIN

#include &quot;catch.hpp&quot;

#include &quot;your_vector_function.hpp&quot;

TEST_CASE(&quot;Increase vector elements by 4&quot;) {

    std::vector&lt;int&gt; vec = {1, 2, 3, 4, 5};

    std::vector&lt;int&gt; expected = {5, 6, 7, 8, 9};

    std::vector&lt;int&gt; result = increaseVector(vec, 4);

    REQUIRE(result == expected);
}

TEST_CASE(&quot;Increase empty vector by 4&quot;) {

    std::vector&lt;int&gt; vec;

    std::vector&lt;int&gt; expected;

    std::vector&lt;int&gt; result = increaseVector(vec, 4);

    REQUIRE(result == expected);
}
