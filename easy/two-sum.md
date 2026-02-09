The Problem:
    Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

    You may assume that each input would have exactly one solution, and you may not use the same element twice.

    You can return the answer in any order.

    Ex1:
        Input: nums = [2,7,11,15], target = 9
        Output: [0,1]
        Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
    Ex2:
        Input: nums = [3,2,4], target = 6
        Output: [1,2]
    Ex3:
        Input: nums = [3,3], target = 6
        Output: [0,1]

Algoritm Thinking:

    Straight forward, Via Brute Force bisa liat kalau ini perlu looping i dan j, i start di = 0 j start di 1 tapi j harus setelah i, cari terus sampe dapet dan jadikan i dan j jadi output array.

Implementing Algorithm:

    public int[] twoSum(int[] nums, int target) {
        List solution = new ArrayList();
        for (int i = 0; i < nums.length; i++) { 
            for (int j = i + 1; j < nums.length; j++) { 
                if (nums[i] + nums[j] == target) { 
                    return new int[] { i, j };
                }
            }
        }
        return new int[] {};
    }
